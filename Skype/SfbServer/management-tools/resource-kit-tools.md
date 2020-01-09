---
title: Documentation sur les outils du Kit de ressources techniques Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/20/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
description: Cette rubrique décrit les outils disponibles dans le kit de ressources de Skype entreprise Server 2015, ainsi que l’objet de chaque outil et des exemples de son utilisation. Le kit de ressources de Skype entreprise Server 2015 vous aide à simplifier les tâches routinières pour les administrateurs informatiques qui déploient et gèrent Skype entreprise Server 2015. Par exemple, l’outil Web Conf Data permet de contrôler aisément les données téléchargées par les utilisateurs au cours d’une réunion en ligne. L’outil SEFAUtil permet de définir le transfert des appels de délégué et le répondeur automatique pour les utilisateurs. Nous recommandons aux administrateurs informatiques d’utiliser ces outils pour gérer plus efficacement Skype entreprise Server 2015.
ms.openlocfilehash: 0087f4286246833f0266ad0c78636bad00167756
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992531"
---
# <a name="skype-for-business-server-2015-resource-kit-tools-documentation"></a><span data-ttu-id="7bcd9-107">Documentation sur les outils du Kit de ressources techniques Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="7bcd9-107">Skype for Business Server 2015 Resource Kit Tools Documentation</span></span>

<span data-ttu-id="7bcd9-108">Cette rubrique décrit les outils disponibles dans le kit de ressources de Skype entreprise Server 2015, ainsi que l’objet de chaque outil et des exemples de son utilisation.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-108">This topic describes the tools in the Skype for Business Server 2015 Resource Kit, including the purpose of each tool, and examples of its use.</span></span> <span data-ttu-id="7bcd9-109">Le kit de ressources de Skype entreprise Server 2015 vous aide à simplifier les tâches routinières pour les administrateurs informatiques qui déploient et gèrent Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-109">The Skype for Business Server 2015 Resource Kit helps to make routine tasks easier for IT administrators who deploy and manage Skype for Business Server 2015.</span></span> <span data-ttu-id="7bcd9-110">Par exemple, l’outil **Web Conf Data** permet de contrôler aisément les données téléchargées par les utilisateurs au cours d’une réunion en ligne.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-110">For example, the **Web Conf Data** tool can be used to easily control data that is uploaded by users during an online meeting.</span></span> <span data-ttu-id="7bcd9-111">L’outil **SEFAUtil** permet de définir le transfert des appels de délégué et le répondeur automatique pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-111">The **SEFAUtil** tool can be used to set up delegate call forwarding and answering for users.</span></span> <span data-ttu-id="7bcd9-112">Nous recommandons aux administrateurs informatiques d’utiliser ces outils pour gérer plus efficacement Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-112">We encourage IT administrators to use these tools to more effectively manage Skype for Business Server 2015.</span></span>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="7bcd9-113">Installation des outils du kit de ressources</span><span class="sxs-lookup"><span data-stu-id="7bcd9-113">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="7bcd9-114">Pour installer le kit de ressources de Skype entreprise Server 2015, téléchargez [OCSReskit. msi](https://www.microsoft.com/en-us/download/details.aspx?id=52631) à partir du centre de téléchargement.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-114">To install the Skype for Business Server 2015 Resource Kit, download [OCSReskit.msi](https://www.microsoft.com/en-us/download/details.aspx?id=52631) from the Download Center.</span></span>

<span data-ttu-id="7bcd9-p103">Exécutez \*\*OCSResKit.msi \*\* pour effectuer une installation simple. Le fichier .msi installe tous les outils dans le chemin d’accès suivant :  **%Program Files%\Skype for Business Server 2015\ResKit**. Les outils exécutables autonomes se trouvent dans ce dossier. Les outils comportant également des fichiers de prise en charge se trouvent dans leur propre sous-dossier.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-p103">Run **OCSResKit.msi** to do a simple installation. The .msi installs all the tools in the following path: **%Program Files%\Skype for Business Server 2015\ResKit**. Tools that are self-contained executables are in this folder. Tools that also have supporting files are in their own subfolders.</span></span>

## <a name="supported-environments"></a><span data-ttu-id="7bcd9-119">Environnements pris en charge</span><span class="sxs-lookup"><span data-stu-id="7bcd9-119">Supported Environments</span></span>

<span data-ttu-id="7bcd9-120">Le kit de ressources de Skype entreprise Server 2015 doit être installé sur un serveur qui répond aux spécifications requises pour Skype entreprise Server 2015, généralement une utilisation pour exécuter Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-120">The Skype for Business Server 2015 Resource Kit should be installed on a server that meets the specifications required for Skype for Business Server 2015, usually one being used to run Skype for Business Server 2015.</span></span>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="7bcd9-121">Présentation des outils du kit de ressources</span><span class="sxs-lookup"><span data-stu-id="7bcd9-121">Resource Kit Tools Overview</span></span>

<span data-ttu-id="7bcd9-122">La liste suivante répertorie les outils fournis dans le kit de ressources de Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-122">The following is a list of the tools that are provided in the Skype for Business Server 2015 Resource Kit.</span></span> <span data-ttu-id="7bcd9-123">Une description de chaque outil (configuration requise et exemple d’utilisation compris) est incluse dans les sections suivantes.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-123">A description of each tool, including the requirements and example usage is covered in the following sections.</span></span>

- [<span data-ttu-id="7bcd9-124">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="7bcd9-124">ABSConfig</span></span>](resource-kit-tools.md#ABSConfig)

- [<span data-ttu-id="7bcd9-125">Bandwidth Policy Service Monitor</span><span class="sxs-lookup"><span data-stu-id="7bcd9-125">Bandwidth Policy Service Monitor</span></span>](resource-kit-tools.md#bpsm)

- [<span data-ttu-id="7bcd9-126">Bandwidth Utilization Analyzer</span><span class="sxs-lookup"><span data-stu-id="7bcd9-126">Bandwidth Utilization Analyzer</span></span>](resource-kit-tools.md#bua)

- [<span data-ttu-id="7bcd9-127">Call Parkometer</span><span class="sxs-lookup"><span data-stu-id="7bcd9-127">Call Parkometer</span></span>](resource-kit-tools.md#callpark)

- [<span data-ttu-id="7bcd9-128">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="7bcd9-128">DBAnalyze</span></span>](resource-kit-tools.md#dba)

- [<span data-ttu-id="7bcd9-129">Import Storage Service Data</span><span class="sxs-lookup"><span data-stu-id="7bcd9-129">Import Storage Service Data</span></span>](resource-kit-tools.md#Issd)

- [<span data-ttu-id="7bcd9-130">LCSSync</span><span class="sxs-lookup"><span data-stu-id="7bcd9-130">LCSSync</span></span>](resource-kit-tools.md#LCSSync)

- [<span data-ttu-id="7bcd9-131">Lookup User Console</span><span class="sxs-lookup"><span data-stu-id="7bcd9-131">Lookup User Console</span></span>](resource-kit-tools.md#LUC)

- [<span data-ttu-id="7bcd9-132">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="7bcd9-132">MsTurnPing</span></span>](resource-kit-tools.md#MsTurnPing)

- [<span data-ttu-id="7bcd9-133">Network Configuration Viewer</span><span class="sxs-lookup"><span data-stu-id="7bcd9-133">Network Configuration Viewer</span></span>](resource-kit-tools.md#NCV)

- [<span data-ttu-id="7bcd9-134">Response Group Agent Live</span><span class="sxs-lookup"><span data-stu-id="7bcd9-134">Response Group Agent Live</span></span>](resource-kit-tools.md#RGAL)

- [<span data-ttu-id="7bcd9-135">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="7bcd9-135">SEFAUtil</span></span>](resource-kit-tools.md#SEFAUtil)

- [<span data-ttu-id="7bcd9-136">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="7bcd9-136">SYSPrep.ps1</span></span>](resource-kit-tools.md#SYSPrep)

- [<span data-ttu-id="7bcd9-137">Unassigned Number Announcements Migration</span><span class="sxs-lookup"><span data-stu-id="7bcd9-137">Unassigned Number Announcements Migration</span></span>](resource-kit-tools.md#UNAM)

- [<span data-ttu-id="7bcd9-138">Web Conf Data</span><span class="sxs-lookup"><span data-stu-id="7bcd9-138">Web Conf Data</span></span>](resource-kit-tools.md#WebConfData)

## <a name="absconfig"></a><span data-ttu-id="7bcd9-139">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="7bcd9-139">ABSConfig</span></span>
<span data-ttu-id="7bcd9-140"><a name="ABSConfig"> </a></span><span class="sxs-lookup"><span data-stu-id="7bcd9-140"></span></span>

<span data-ttu-id="7bcd9-141">L’outil de configuration du service de carnet d’adresses (ABSConfig) est un outil administratif qui permet aux administrateurs de personnaliser la configuration du service de carnet d’adresses dans Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-141">The Address Book Service Configuration tool (ABSConfig) is an administrative tool that helps administrators customize Address Book Service configuration in Skype for Business Server 2015.</span></span> <span data-ttu-id="7bcd9-142">Cet outil permet également aux administrateurs 2015 de Skype entreprise Server de restaurer les paramètres de service de carnet d’adresses par défaut.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-142">This tool also enables Skype for Business Server 2015 administrators to restore the default Address Book Service settings.</span></span>

### <a name="description"></a><span data-ttu-id="7bcd9-143">Description</span><span class="sxs-lookup"><span data-stu-id="7bcd9-143">Description</span></span>

<span data-ttu-id="7bcd9-144">ABSConfig est une application graphique d’interface utilisateur qui permet aux administrateurs de configurer des attributs de services de domaine Active Directory liés au service de carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-144">ABSConfig is a graphical user interface application that enables administrators to configure Active Directory Domain Services attributes that are related to Address Book Service.</span></span>

<span data-ttu-id="7bcd9-145">Les principaux scénarios suivants s’appliquent à l’outil :</span><span class="sxs-lookup"><span data-stu-id="7bcd9-145">The primary scenarios for the tool are the following:</span></span>

- <span data-ttu-id="7bcd9-146">Pour permettre aux administrateurs de mapper les attributs dans les services de domaine Active Directory aux attributs de Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-146">To enable administrators to map attributes in Active Directory Domain Services to the attributes for Skype for Business Server 2015.</span></span>

- <span data-ttu-id="7bcd9-147">permettre aux administrateurs de spécifier un attribut des services de domaine Active Directory à inclure dans les fichiers du service de carnet d’adresses ou à exclure de ceux-ci ;</span><span class="sxs-lookup"><span data-stu-id="7bcd9-147">To enable administrators to specify the Active Directory Domain Services attribute to be included or excluded in the Address Book Service files.</span></span>

- <span data-ttu-id="7bcd9-148">permettre aux administrateurs de restaurer les paramètres par défaut du service de carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-148">To enable administrators to restore default Address Book Service settings.</span></span>

<span data-ttu-id="7bcd9-149">L’outil ABSConfig peut être démarré à l’aide du fichier ABSConfig.exe.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-149">The ABSConfig tool can be started by using the ABSConfig.exe file.</span></span> <span data-ttu-id="7bcd9-150">L’outil s’ouvre dans l’onglet **configurer les attributs** . Ce tableau propose des options permettant de mapper les attributs des services de domaine Active Directory aux champs d’attribut pour Skype entreprise Server 2015 et de spécifier les utilisateurs à inclure ou à exclure dans les fichiers du service de carnet d’adresses en fonction de filtres d’attributs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-150">The tool opens to the **Configure Attributes** tab. This table has options to map Active Directory Domain Services attributes to the attribute fields for Skype for Business Server 2015 and to specify which users to include or exclude in Address Book Service files based on specific attribute filters.</span></span> <span data-ttu-id="7bcd9-151">D’autres options permettent de personnaliser la valeur du numéro de téléphone à inclure dans le fichier de carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-151">It also has options to customize which value of the phone number to be included in the Address Book file.</span></span> <span data-ttu-id="7bcd9-152">L’option \*\*Restore Defaults (Paramètres par défaut) \*\* permet aux administrateurs de restaurer les valeurs par défaut des paramètres du service de carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-152">The **Restore Defaults** option enables administrators to restore Address Book Service settings to default values.</span></span>

> [!NOTE]
> <span data-ttu-id="7bcd9-153">Le fait de remapper les attributs AD aux différents noms de champs OC fonctionne uniquement pour le téléchargement du fichier du carnet d’adresses et n’est pas pris en charge par la requête Web du carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-153">Re-mapping of AD attributes to different OC Field Names will only work for Address Book File Download, and is not supported by Address Book Web Query.</span></span>

### <a name="output"></a><span data-ttu-id="7bcd9-154">Sortie</span><span class="sxs-lookup"><span data-stu-id="7bcd9-154">Output</span></span>

<span data-ttu-id="7bcd9-155">ABSConfig stocke la configuration du service de carnet d’adresses dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-155">ABSConfig stores the Address Book Service configuration in the database.</span></span>

```PowerShell
Path: %ProgramFiles%\Skype for Business Server 2015\Reskit
```

### <a name="purpose"></a><span data-ttu-id="7bcd9-156">Objectif</span><span class="sxs-lookup"><span data-stu-id="7bcd9-156">Purpose</span></span>

<span data-ttu-id="7bcd9-157">ABSConfig offre un moyen rapide et facile de personnaliser le service de carnet d’adresses de Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-157">ABSConfig provides a quick and easy way to customize Skype for Business Server 2015 Address Book Service.</span></span>

### <a name="requirements"></a><span data-ttu-id="7bcd9-158">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="7bcd9-158">Requirements</span></span>

#### <a name="computer"></a><span data-ttu-id="7bcd9-159">Ordinateur</span><span class="sxs-lookup"><span data-stu-id="7bcd9-159">Computer</span></span>

<span data-ttu-id="7bcd9-160">ABSConfig ne peut être exécuté qu’à partir d’un ordinateur appartenant à un domaine sur lequel Skype entreprise Server 2015 est installé.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-160">ABSConfig can be run only from a domain-joined computer that has Skype for Business Server 2015 installed.</span></span> <span data-ttu-id="7bcd9-161">Dans le cas de Skype entreprise Server 2015, Enterprise Edition, cet outil peut être exécuté sur n’importe quel serveur frontal sur lequel le service de carnet d’adresses est activé lors de l’installation.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-161">In the case of Skype for Business Server 2015, Enterprise Edition, this tool can be run on any Front End servers that have the Address Book Service enabled during setup.</span></span>

#### <a name="network"></a><span data-ttu-id="7bcd9-162">Réseau</span><span class="sxs-lookup"><span data-stu-id="7bcd9-162">Network</span></span>

<span data-ttu-id="7bcd9-163">L’ordinateur doit pouvoir se connecter au pool frontal et à la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-163">The computer should be able to connect to the Front End pool and back-end database.</span></span>

#### <a name="software"></a><span data-ttu-id="7bcd9-164">Logiciels</span><span class="sxs-lookup"><span data-stu-id="7bcd9-164">Software</span></span>

<span data-ttu-id="7bcd9-165">Les composants logiciels suivants doivent être installés avant d’exécuter l’outil ABSConfig :</span><span class="sxs-lookup"><span data-stu-id="7bcd9-165">The following software components must be installed before running the ABSConfig tool:</span></span>

- <span data-ttu-id="7bcd9-166">Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="7bcd9-166">Skype for Business Server 2015</span></span>

#### <a name="users"></a><span data-ttu-id="7bcd9-167">Utilisateurs</span><span class="sxs-lookup"><span data-stu-id="7bcd9-167">Users</span></span>

<span data-ttu-id="7bcd9-168">Administrateurs disposant des autorisations requises pour mettre à jour le déploiement de Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-168">Administrators who have the permissions required to update the Skype for Business Server 2015 deployment.</span></span>

### <a name="examples"></a><span data-ttu-id="7bcd9-169">Exemples</span><span class="sxs-lookup"><span data-stu-id="7bcd9-169">Examples</span></span>

<span data-ttu-id="7bcd9-p108">ABSConfig peut être démarré en tapant **ABSConfig.exe** dans une invite de commandes. L’interface utilisateur de l’outil ABSConfig se présente comme suit :</span><span class="sxs-lookup"><span data-stu-id="7bcd9-p108">ABSConfig can be started by typing **ABSConfig.exe** at a command prompt. Shown below is the ABSConfig tool user interface.</span></span>

![Outil ABSConfig. exe.](../media/Reskit_2012_Tools_Documentation_ABSConfig.JPG)

### <a name="summary"></a><span data-ttu-id="7bcd9-173">Résumé</span><span class="sxs-lookup"><span data-stu-id="7bcd9-173">Summary</span></span>

<span data-ttu-id="7bcd9-174">L’outil ABSConfig fournit aux administrateurs un outil rapide et facile à utiliser pour personnaliser le service de carnet d’adresses de Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-174">The ABSConfig tool provides administrators a quick and easy to use tool to customize Skype for Business Server 2015 Address Book Service.</span></span>

## <a name="bandwidth-policy-service-monitor"></a><span data-ttu-id="7bcd9-175">Bandwidth Policy Service Monitor</span><span class="sxs-lookup"><span data-stu-id="7bcd9-175">Bandwidth Policy Service Monitor</span></span>
<span data-ttu-id="7bcd9-176"><a name="bpsm"> </a></span><span class="sxs-lookup"><span data-stu-id="7bcd9-176"></span></span>

<span data-ttu-id="7bcd9-177">L’outil Bandwidth Policy Service Monitor permet aux administrateurs d’afficher la liste des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="7bcd9-177">The Bandwidth Policy Service Monitor tool is intended to allow administrators to view a list of the following:</span></span>

1. <span data-ttu-id="7bcd9-178">Tous les services de stratégie de bande passante configurés pour Skype entreprise Server 2015 (authentification et noyau) dans la topologie</span><span class="sxs-lookup"><span data-stu-id="7bcd9-178">All the configured Skype for Business Server 2015 Bandwidth Policy services (Authentication and Core) in the topology</span></span>

2. <span data-ttu-id="7bcd9-179">connexions effectuées par chaque service aux autres services de stratégie de bande passante et aux serveurs Edge ;</span><span class="sxs-lookup"><span data-stu-id="7bcd9-179">The connections that each service makes to other Bandwidth Policy services and to the Edge servers</span></span>

3. <span data-ttu-id="7bcd9-180">liaisons configurées dans le document de configuration du réseau et utilisation de la bande passante en temps réel, telle que signalée par les services de stratégie de bande passante individuels.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-180">All the links that are configured in the Network configuration document and real-time bandwidth usage as reported by each of the Bandwidth Policy services</span></span>

### <a name="description"></a><span data-ttu-id="7bcd9-181">Description</span><span class="sxs-lookup"><span data-stu-id="7bcd9-181">Description</span></span>

<span data-ttu-id="7bcd9-p109">L’outil Bandwidth Policy Service Monitor est implémenté sous la forme d’une application à interface utilisateur graphique. Les administrateurs démarrent l’outil en exécutant PDPMonUI.exe.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-p109">The Bandwidth Policy Service Monitor tool is implemented as a GUI-based application. Administrators start the tool by running PDPMonUI.exe.</span></span>

<span data-ttu-id="7bcd9-p110">Lorsque l’outil démarre, il tente de découvrir la liste des services de stratégie de bande passante dans la topologie. Une fois la mise à jour initiale effectuée, le volet situé à gauche de la fenêtre reçoit une liste de services regroupés selon les clusters auxquels ils appartiennent.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-p110">When the tool starts, it attempts to discover the list of Bandwidth Policy services in the topology. After the initial update is done, the pane to the left of the window is populated with a list of services that are grouped by the clusters that they belong to.</span></span>

<span data-ttu-id="7bcd9-p111">Lorsque les administrateurs sélectionnent un service de stratégie de bande passante particulier, le volet situé à droite affiche les informations relatives à ce service particulier. Ce volet inclut également deux onglets principaux qui affichent des informations.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-p111">When administrators select a particular Bandwidth Policy Service, the pane on the right displays the information about that particular service. That pane also has two main tabs that display information.</span></span>

#### <a name="machine-info-tab"></a><span data-ttu-id="7bcd9-188">Onglet Machine Info (Informations sur l’ordinateur)</span><span class="sxs-lookup"><span data-stu-id="7bcd9-188">Machine Info Tab</span></span>

<span data-ttu-id="7bcd9-189">L’onglet **Machine Info (Informations sur l’ordinateur)** fournit des informations sur le service de stratégie de bande passante sélectionné, ainsi que la liste et l’état des connexions effectuées par le service de stratégie de bande passante sélectionné aux autres services.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-189">The **Machine Info** tab shows the details of the Bandwidth Policy Service that is selected and the list and state of all the connections that are made by the selected Bandwidth Policy Service to other services.</span></span>

#### <a name="topology-info-tab"></a><span data-ttu-id="7bcd9-190">Onglet Topology Info (Informations sur la topologie)</span><span class="sxs-lookup"><span data-stu-id="7bcd9-190">Topology Info Tab</span></span>

<span data-ttu-id="7bcd9-p112">L’onglet **Topology Info (Informations sur la topologie)** affiche la liste des liaisons configurées dans les paramètres de configuration du réseau. Pour chaque liaison, la capacité de bande passante audio et vidéo est indiquée. La bande passante actuellement utilisée est également indiquée, en Kbps et en pourcentage de la capacité. L’outil utilise des couleurs pour mettre en valeur les liaisons dont l’utilisation atteint presque la capacité maximale afin que les administrateurs puissent les isoler rapidement.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-p112">The **Topology Info** tab shows a list of all the links that are configured in the Network configuration settings. For each link, the audio and video bandwidth capacity is displayed. Additionally, the currently utilized bandwidth is displayed, both in Kbps and as a percentage of the capacity. The tool uses color-coding to highlight links that have utilization that is close to the capacity—this allows administrators to quickly isolate such links.</span></span>

> [!NOTE]
>  <span data-ttu-id="7bcd9-195">Si l’outil Moniteur du service de stratégie de bande passante rencontre une défaillance lorsqu’il se connecte à un service de stratégie de bande passante configuré, les informations figurant dans les onglets informations sur l' **ordinateur** et **informations de topologie** ne sont pas remplies.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-195">If the Bandwidth Policy Service Monitor tool experiences failure when it connects to any of the configured Bandwidth Policy services, the information in the **Machine Info** and the **Topology Info** tabs won't be populated.</span></span> <span data-ttu-id="7bcd9-196">Il est toutefois possible que l’outil se connecte avant de perdre la connexion au service.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-196">However, it is possible that the tool might connect initially but subsequently lose its connection to the service.</span></span> <span data-ttu-id="7bcd9-197">En pareil cas, les administrateurs peuvent voir des informations obsolètes.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-197">In such cases, administrators might see outdated information.</span></span> <span data-ttu-id="7bcd9-198">Les onglets incluent des informations d’horodatage (**Last Updated (Dernière mise à jour)**) qui permettent aux administrateurs de voir la date/l’heure de la dernière mise à jour des données pour un service de stratégie de bande passante particulier.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-198">There is a **Last Updated** time stamp on each of the tabs that can allow administrators to see when the data was last updated for a particular Bandwidth Policy Service.</span></span>

### <a name="output"></a><span data-ttu-id="7bcd9-199">Sortie</span><span class="sxs-lookup"><span data-stu-id="7bcd9-199">Output</span></span>

<span data-ttu-id="7bcd9-200">Il n’y a aucune sortie de ligne de commande. La sortie du programme apparaît dans l’interface utilisateur graphique principale.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-200">There is no command-line output; the program output is contained within the main graphical user interface (GUI).</span></span>

### <a name="purpose"></a><span data-ttu-id="7bcd9-201">Objectif</span><span class="sxs-lookup"><span data-stu-id="7bcd9-201">Purpose</span></span>

<span data-ttu-id="7bcd9-p114">L’outil Bandwidth Policy Service Monitor permet aux administrateurs de consulter l’état des services de stratégie de bande passante définis dans la topologie. Ils peuvent également voir l’utilisation de la bande passante en temps réel pour toutes les liaisons définies dans le document de configuration du réseau.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-p114">The purpose of the Bandwidth Policy Service Monitor tool is to allow administrators visibility into the state of each of the Bandwidth Policy services that are defined in the topology. In addition, administrators can see real-time bandwidth usage for all the links that are defined in the Network configuration document.</span></span>

### <a name="requirements"></a><span data-ttu-id="7bcd9-204">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="7bcd9-204">Requirements</span></span>

<span data-ttu-id="7bcd9-205">L’outil Moniteur du service de stratégie de bande passante doit être exécuté sur un ordinateur qui fait partie de la topologie de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-205">The Bandwidth Policy Service Monitor tool needs to be run on a computer that is part of the Skype for Business Server topology.</span></span>

### <a name="summary"></a><span data-ttu-id="7bcd9-206">Résumé</span><span class="sxs-lookup"><span data-stu-id="7bcd9-206">Summary</span></span>

<span data-ttu-id="7bcd9-207">L’outil Bandwidth Policy Service Monitor est utile pour contrôler l’état des services de stratégie de bande passante dans la topologie et connaître l’utilisation de la bande passante en temps réel pour les liaisons définies dans les paramètres de configuration du réseau.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-207">The Bandwidth Policy Service Monitor tool can be a valuable resource to administrators so they can inspect the state of all the Bandwidth Policy services in the topology—and more importantly—they can obtain real-time bandwidth utilization for the links that are defined in the Network configuration settings.</span></span>

## <a name="bandwidth-utilization-analyzer"></a><span data-ttu-id="7bcd9-208">Bandwidth Utilization Analyzer</span><span class="sxs-lookup"><span data-stu-id="7bcd9-208">Bandwidth Utilization Analyzer</span></span>
<span data-ttu-id="7bcd9-209"><a name="bua"> </a></span><span class="sxs-lookup"><span data-stu-id="7bcd9-209"></span></span>

<span data-ttu-id="7bcd9-p115">L’outil Bandwidth Utilization Analyzer crée des rapports sur divers affichages de la consommation de bande passante par les points de terminaison d’UC entre les liaisons de réseau étendu dans le réseau d’entreprise. Ces rapports permettent d’identifier le modèle actuel de consommation de la bande passante et de planifier la capacité de bande passante.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-p115">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network. These reports can be used to understand the current bandwidth consumption pattern and to aid in bandwidth capacity planning.</span></span>

### <a name="description"></a><span data-ttu-id="7bcd9-212">Description</span><span class="sxs-lookup"><span data-stu-id="7bcd9-212">Description</span></span>

<span data-ttu-id="7bcd9-p116">Bandwidth Utilization Analyzer est implémenté sous la forme d’une application à interface utilisateur graphique. Cet outil génère des rapports spécifiques sur l’utilisation de la bande passante audio dans le réseau et constitue une aide pour planifier la capacité. Il traite également la capacité de bande passante affectée aux diverses liaisons par itération.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-p116">Bandwidth Utilization Analyzer is implemented as a GUI-based application. This tool generates reports specifically for audio utilization across the network and helps with capacity planning. It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

### <a name="output"></a><span data-ttu-id="7bcd9-216">Sortie</span><span class="sxs-lookup"><span data-stu-id="7bcd9-216">Output</span></span>

<span data-ttu-id="7bcd9-217">Bandwidth Utilization Analyzer offre une représentation graphique de la capacité de bande passante et de l’utilisation de la bande passante audio pour les liaisons de réseau étendu configurées dans le système.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-217">Bandwidth Utilization Analyzer provides graphic al plots of bandwidth capacity and utilization for audio for all the WAN links that are configured in the system.</span></span>

### <a name="purpose"></a><span data-ttu-id="7bcd9-218">Objectif</span><span class="sxs-lookup"><span data-stu-id="7bcd9-218">Purpose</span></span>

<span data-ttu-id="7bcd9-219">Dans n’importe quel déploiement audio et vidéo, il est essentiel de surveiller et de comprendre la tendance de l’utilisation de la bande passante du trafic multimédia sur le réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-219">In any voice and video deployment, it's critical to monitor and understand the trend of bandwidth utilization of media traffic across the enterprise network.</span></span> <span data-ttu-id="7bcd9-220">L’outil Bandwidth Utilization Analyzer permet aux administrateurs d’y parvenir.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-220">The Bandwidth Utilization Analyzer tool allows an administrator to achieve just that.</span></span> <span data-ttu-id="7bcd9-221">L’outil effectue les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="7bcd9-221">This tool does the following:</span></span>

- <span data-ttu-id="7bcd9-222">génère des rapports spécifiques sur l’utilisation de la bande passante audio dans le réseau ;</span><span class="sxs-lookup"><span data-stu-id="7bcd9-222">Generates specific reports for audio utilization across the network</span></span>

- <span data-ttu-id="7bcd9-223">permet de planifier la capacité plus efficacement et de traiter la capacité de bande passante affectée aux diverses liaisons par itération.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-223">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="7bcd9-224">Bandwidth Utilization Analyzer peut générer une représentation graphique des rapports sur la capacité et l’utilisation de la bande passante, comme suit :</span><span class="sxs-lookup"><span data-stu-id="7bcd9-224">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and utilization reports; they are as follows:</span></span>

- <span data-ttu-id="7bcd9-225">liaisons de réseau étendu au sein du réseau d’entreprise ;</span><span class="sxs-lookup"><span data-stu-id="7bcd9-225">All the WAN links in the enterprise network</span></span>

- <span data-ttu-id="7bcd9-226">filtrage des liaisons de réseau étendu sélectionnées ;</span><span class="sxs-lookup"><span data-stu-id="7bcd9-226">Filtered by selected WAN links that have been chosen</span></span>

- <span data-ttu-id="7bcd9-227">filtrage des liaisons de réseau étendu ayant dépassé leur capacité ;</span><span class="sxs-lookup"><span data-stu-id="7bcd9-227">Filtered by WAN links that have exceeded link capacity</span></span>

- <span data-ttu-id="7bcd9-228">filtrage des liaisons de réseau étendu ayant sous-utilisé la bande passante approvisionnée ;</span><span class="sxs-lookup"><span data-stu-id="7bcd9-228">Filtered by WAN links that have been under-utilizing the provisioned bandwidth</span></span>

- <span data-ttu-id="7bcd9-229">filtrage des liaisons de réseau étendu ayant atteint des niveaux critiques (utilisation de la bande passante supérieure à 90 % de la capacité de bande passante de la liaison de réseau étendu) ;</span><span class="sxs-lookup"><span data-stu-id="7bcd9-229">Filter by WAN links that have been reaching critical levels (a bandwidth utilization that is greater than 90% of bandwidth capacity of the WAN link)</span></span>

- <span data-ttu-id="7bcd9-230">filtrage selon le type de liaison de réseau étendu (liaisons réseau-site, liaisons inter-régions et liaisons au sein d’un site) ;</span><span class="sxs-lookup"><span data-stu-id="7bcd9-230">Filtered by WAN link type—network-site links, interregional links, and links within a site</span></span>

- <span data-ttu-id="7bcd9-231">filtrage par région réseau.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-231">Filtered by network region</span></span>

#### <a name="applications"></a><span data-ttu-id="7bcd9-232">Applications</span><span class="sxs-lookup"><span data-stu-id="7bcd9-232">Applications</span></span>

<span data-ttu-id="7bcd9-233">Bandwidth Utilization Analyzer inclut les deux applications (outils) suivantes :</span><span class="sxs-lookup"><span data-stu-id="7bcd9-233">Bandwidth Utilization Analyzer has the following two applications (tools):</span></span>

- <span data-ttu-id="7bcd9-234">**WanLinkLogCollector. exe** cet outil permet à l’utilisateur d’entrer les informations requises.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-234">**WanLinkLogCollector.exe** This tool enables its user to input the required information.</span></span>

- <span data-ttu-id="7bcd9-235">**BandwidthUtilizationAnalyzer. xlsm** un rapport de feuille de calcul Microsoft Excel est automatiquement lancé par WanLinkLogCollector. exe.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-235">**BandwidthUtilizationAnalyzer.xlsm** A Microsoft Excel spreadsheet software report is automatically launched by WanLinkLogCollector.exe.</span></span> <span data-ttu-id="7bcd9-236">Cette application permet à l’utilisateur d’appliquer des filtres au rapport, comme indiqué plus loin dans cet article.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-236">This application allows the user to apply filters to the report as shown later in this article.</span></span>

#### <a name="phases-of-using-bandwidth-utilization-analyzer"></a><span data-ttu-id="7bcd9-237">Phases d’utilisation de Bandwidth Utilization Analyzer</span><span class="sxs-lookup"><span data-stu-id="7bcd9-237">Phases of Using Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="7bcd9-238">L’utilisation de Bandwidth Utilization Analyzer implique deux phases :</span><span class="sxs-lookup"><span data-stu-id="7bcd9-238">There are two phases when using Bandwidth Utilization Analyzer:</span></span>

- <span data-ttu-id="7bcd9-239">collecte des journaux, effectuée à l’aide de WanLinkLogCollector.exe ;</span><span class="sxs-lookup"><span data-stu-id="7bcd9-239">Collect logs, which is performed by using WanLinkLogCollector.exe</span></span>

- <span data-ttu-id="7bcd9-240">personnalisation des rapports, effectuée à l’aide de BandwidthUtilizationAnalyzer.xlsm.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-240">Customize reports, which is performed by using BandwidthUtilizationAnalyzer.xlsm</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7bcd9-241">Il est recommandé que BandwidthUtilizationAnalyzer.xlsm ne soit pas démarré manuellement par les utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-241">We strongly recommend that BandwidthUtilizationAnalyzer.xlsm not be manually launched by end users.</span></span>

#### <a name="starting-bandwidth-utilization-analyzer"></a><span data-ttu-id="7bcd9-242">Démarrage de Bandwidth Utilization Analyzer</span><span class="sxs-lookup"><span data-stu-id="7bcd9-242">Starting Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="7bcd9-243">Démarrez WanLinkLogCollector.exe dans une invite de commandes ou à l’aide de l’Explorateur Windows.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-243">Start WanLinkLogCollector.exe at the command prompt or by using Windows Explorer.</span></span>

 <span data-ttu-id="7bcd9-244">**Utilisation de WanLinkLogCollector.exe**</span><span class="sxs-lookup"><span data-stu-id="7bcd9-244">**Using WanLinkLogCollector.exe**</span></span>

<span data-ttu-id="7bcd9-245">L’utilisation de WanLinkLogCollector.exe comporte trois étapes :</span><span class="sxs-lookup"><span data-stu-id="7bcd9-245">There are three steps to using WanLinkLogCollector.exe:</span></span>

1. <span data-ttu-id="7bcd9-246">**Journalisation de la chronologie** Indiquer la chronologie à laquelle le rapport doit être généré</span><span class="sxs-lookup"><span data-stu-id="7bcd9-246">**Log the timeline** Provide the timeline that the report needs to be generated for</span></span>

2. <span data-ttu-id="7bcd9-247">**Spécifier les répertoires de fichiers** Fournir des informations sur l’emplacement des fichiers</span><span class="sxs-lookup"><span data-stu-id="7bcd9-247">**Specify the file directories** Provide file location information</span></span>

3. <span data-ttu-id="7bcd9-248">**Collecter les journaux et lancer la visionneuse de rapports** Exécuter la commande pour générer le rapport</span><span class="sxs-lookup"><span data-stu-id="7bcd9-248">**Collect the logs and launch the report viewer** Execute the command to generate the report</span></span>

#### <a name="step-1---log-the-timeline"></a><span data-ttu-id="7bcd9-249">Étape 1 - Définition de la chronologie</span><span class="sxs-lookup"><span data-stu-id="7bcd9-249">Step 1 - Log the timeline</span></span>

<span data-ttu-id="7bcd9-250">La définition de la chronologie permet à l’utilisateur de l’outil de spécifier les éléments suivants, comme indiqué dans la figure suivante. </span><span class="sxs-lookup"><span data-stu-id="7bcd9-250">Logging the timeline allows the tool user to specify the following as shown in the figure below.</span></span>

1. <span data-ttu-id="7bcd9-251">**Date de début** Date de début de la chronologie pour laquelle le rapport doit être généré (par exemple, 1er août 2010).</span><span class="sxs-lookup"><span data-stu-id="7bcd9-251">**Start date** This is the start date of the timeline that the report is to be generated for; for example, August 1, 2010.</span></span>

2. <span data-ttu-id="7bcd9-252">**Date de fin** Date de fin de la chronologie pour laquelle le rapport doit être généré (par exemple, 30 septembre 2010).</span><span class="sxs-lookup"><span data-stu-id="7bcd9-252">**End date** This is the end date of the timeline that the report is to be generated for; for example, September 30, 2010.</span></span>

     ![Dates de début et de fin dans l’utilisation de la bande passante A](../media/Reskit_2012_Tools_Documentation_Image4.jpg)

#### <a name="step-2---specify-the-file-directories"></a><span data-ttu-id="7bcd9-254">Étape 2 - Définition des répertoires de fichiers</span><span class="sxs-lookup"><span data-stu-id="7bcd9-254">Step 2 - Specify the file directories</span></span>

<span data-ttu-id="7bcd9-255">Les répertoires de fichiers suivants peuvent être spécifiés par l’utilisateur, comme indiqué.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-255">The following file directories can be specified by the user as shown.</span></span>

- <span data-ttu-id="7bcd9-256">**Emplacement des fichiers journaux du serveur** Emplacement du dossier dans lequel les journaux du serveur de stratégie de bande passante sont stockés.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-256">**Server log files location** The folder location where Bandwidth policy server logs are stored.</span></span> <span data-ttu-id="7bcd9-257">Il s’agit généralement \<de\> \\ l’option FileServer<\>choix de Fe \AppServerFiles\PDP.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-257">This is typically in \<fileserver\>\\<choice of FE\>\AppServerFiles\PDP.</span></span>

- <span data-ttu-id="7bcd9-258">**Emplacement de stockage des fichiers temporaires** Emplacement du fichier temporaire où les fichiers intermédiaires sont stockés lors de la génération du rapport.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-258">**Temporary file storage location** The temporary file location where intermediate files are stored while the report is being generated.</span></span>

![Répertoires de fichiers dans l’utilisation de la bande passante anal](../media/Reskit_2012_Tools_Documentation_Image5.jpg)

> [!NOTE]
> <span data-ttu-id="7bcd9-260">Vérifiez que l’utilisateur de l’outil dispose d’un accès suffisant aux journaux de serveur et au dossier du magasin des fichiers temporaires.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-260">Ensure that sufficient file access to the server logs and the temporary file store folder is provided to the tool user.</span></span>

#### <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a><span data-ttu-id="7bcd9-261">Étape 3 - Collecte des journaux et démarrage de la visionneuse de rapports</span><span class="sxs-lookup"><span data-stu-id="7bcd9-261">Step 3 - Collect the logs and start the report viewer</span></span>

<span data-ttu-id="7bcd9-p120">Pour collecter les journaux et démarrer la visionneuse de rapports, cliquez sur **Execute (Exécuter)** comme indiqué ci-dessous. Cette opération permet de collecter les données requises.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-p120">To collect the logs and start the report viewer, click **Execute** as shown below. This step collects the required data.</span></span>

![Collecte de données dans la Analité de l’utilisation de la bande passante](../media/Reskit_2012_Tools_Documentation_Image6.jpg)

<span data-ttu-id="7bcd9-265">Une fois le contenu saisi validé, le message suivant apparaît.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-265">When the input validation is successful, the message shown below is displayed.</span></span>

![Journaux de notification collectés dans la bande passante utili](../media/Reskit_2012_Tools_Documentation_Image7.jpg)

<span data-ttu-id="7bcd9-p121">Cliquez sur **OK**. BandwidthUtilizationAnalyzer.xlsm démarre automatiquement. Suivez les instructions du message. Pour plus d’informations, voir \*\*Utilisation de BandwidthUtilizationAnalyzer.xlsm \*\* dans la section suivante.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-p121">Click **OK**. BandwidthUtilizationAnalyzer.xlsm is automatically started. Follow the instructions in the message box. For details, see **Using BandwidthUtilizationAnalyzer.xlsm** in the next section.</span></span>


### <a name="using-bandwidthutilizationanalyzerxlsm"></a><span data-ttu-id="7bcd9-271">Utilisation de BandwidthUtilizationAnalyzer.xlsm</span><span class="sxs-lookup"><span data-stu-id="7bcd9-271">Using BandwidthUtilizationAnalyzer.xlsm</span></span>

1. <span data-ttu-id="7bcd9-272">Une fois BandwidthUtilizationAnalyzer.xlsm démarré automatiquement, cliquez sur **Refresh (Actualiser)**, comme indiqué ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-272">When BandwidthUtilizationAnalyzer.xlsm is automatically started, click **Refresh** as shown below.</span></span>

     ![BandwidthUtilizationAnalyzer.xlsm  ](../media/Reskit_2012_Tools_Documentation_Image8.jpg)

2. <span data-ttu-id="7bcd9-p122">Si un dossier de fichiers est ouvert, sélectionnez consolidated.csv à l’emplacement spécifié dans le message, comme indiqué ci-dessous. L’emplacement du répertoire **C:\Temp** est également indiqué.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-p122">When a file folder is opened, select consolidated.csv from the location that is specified in the message box as shown below. It also shows the location as **C:\Temp**.</span></span>

     ![Ouverture d’un dossier dans BandwidthUtilizationAnalyzer.](../media/Reskit_2012_Tools_Documentation_Image9.jpg)

3. <span data-ttu-id="7bcd9-277">Cliquez sur **Import (Importer)**.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-277">Click **Import**.</span></span>

4. <span data-ttu-id="7bcd9-p123">La représentation graphique est générée automatiquement. Elle est disponible lorsque le pointeur de traitement en arrière-plan disparaît.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-p123">The graphical plot is automatically generated. It is available when the working-in-the-background pointer disappears.</span></span>

     ![Application de filtres dans le mode état.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

#### <a name="applying-filters-to-the-report-view"></a><span data-ttu-id="7bcd9-281">Application de filtres à l’affichage du rapport</span><span class="sxs-lookup"><span data-stu-id="7bcd9-281">Applying Filters to the Report View</span></span>

<span data-ttu-id="7bcd9-282">Les filtres suivants peuvent être appliqués à l’affichage du rapport :</span><span class="sxs-lookup"><span data-stu-id="7bcd9-282">The filters that can be applied to the report view as shown below are described as follows:</span></span>

![Application de filtres dans le mode état.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

1. <span data-ttu-id="7bcd9-284">**Name (Nom)** Filtrage des liaisons de réseau étendu (le filtre apparaît dans la partie droite du graphique). Le préfixe représente les types de liaisons suivants (voir l’encadré bleu vertical) :</span><span class="sxs-lookup"><span data-stu-id="7bcd9-284">**Name** Filter by WAN links (the filter is on the right side of the graph).The prefix denotes the following link types; see the vertical (blue) box:</span></span>

   - <span data-ttu-id="7bcd9-285">**S Site (S (site))** Liaison de réseau étendu entre un site réseau et une région réseau</span><span class="sxs-lookup"><span data-stu-id="7bcd9-285">**S Site** The WAN link from a network site to a network region</span></span>

   - <span data-ttu-id="7bcd9-286">**IS Inter-Site (IS (intersite))** Liaison de réseau étendu entre deux sites réseau</span><span class="sxs-lookup"><span data-stu-id="7bcd9-286">**IS Inter-Site** The WAN link between two network sites</span></span>

   - <span data-ttu-id="7bcd9-287">**R Inter-Region (R (inter-régions))** Liaison de réseau étendu entre deux régions réseau</span><span class="sxs-lookup"><span data-stu-id="7bcd9-287">**R Inter-Region** The WAN link between two network region</span></span>

2. <span data-ttu-id="7bcd9-288">**Exceeded limit (Limite dépassée)** Filtrage des liaisons de réseau étendu pour lesquelles l’utilisation de la bande passante est supérieure à la capacité de bande passante</span><span class="sxs-lookup"><span data-stu-id="7bcd9-288">**Exceeded limit** Filter by WAN links whose bandwidth utilization is more than the bandwidth capacity</span></span>

3. <span data-ttu-id="7bcd9-289">**Critical levels (Niveaux critiques)** Filtrage des liaisons de réseau étendu pour lesquelles l’utilisation de la bande passante a atteint 90 % ou plus de la capacité de bande passante</span><span class="sxs-lookup"><span data-stu-id="7bcd9-289">**Critical levels** Filter by WAN links whose bandwidth utilization has reached 90% or more than the bandwidth capacity</span></span>

4. <span data-ttu-id="7bcd9-290">**Under-utilized (Sous-utilisé)** Filtrage des liaisons de réseau étendu pour lesquelles l’utilisation de la bande passante est inférieure à 25 % de la capacité de bande passante</span><span class="sxs-lookup"><span data-stu-id="7bcd9-290">**Under-utilized** Filter by WAN links whose bandwidth utilization has been less than 25% of the bandwidth capacity</span></span>

5. <span data-ttu-id="7bcd9-291">**Link type (Type de liaison)** Filtrage des types de liaisons de réseau étendu suivants :</span><span class="sxs-lookup"><span data-stu-id="7bcd9-291">**Link type** Filter by the following WAN links types:</span></span>

   - <span data-ttu-id="7bcd9-292">**Network site (Site réseau)**</span><span class="sxs-lookup"><span data-stu-id="7bcd9-292">**Network site** type</span></span>

   - <span data-ttu-id="7bcd9-293">**Inter-site (intersite)**</span><span class="sxs-lookup"><span data-stu-id="7bcd9-293">**Inter-site** type</span></span>

   - <span data-ttu-id="7bcd9-294">**Inter-Region (Inter-régions)**</span><span class="sxs-lookup"><span data-stu-id="7bcd9-294">**Inter-Region link** type</span></span>

6. <span data-ttu-id="7bcd9-295">**Region (Région)** Filtrage de la région réseau</span><span class="sxs-lookup"><span data-stu-id="7bcd9-295">**Region** Filter by network region</span></span>

<span data-ttu-id="7bcd9-296">Les figures suivantes présentent les filtres décrits précédemment.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-296">The following figures show the previously described filters.</span></span>

<span data-ttu-id="7bcd9-p124">Filtrage sur **Name (Nom)**. Sélectionnez la liste des liaisons devant être affichées dans le graphique.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-p124">Filter by **Name**. Select the list of links that need to be displayed in the graph.</span></span>

![Filtrage par nom dans BandwidthUtilizationAnalyzer.](../media/Reskit_2012_Tools_Documentation_Image12.jpg)

<span data-ttu-id="7bcd9-300">Filtrage sur **Exceeded limit (Limite dépassée)**.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-300">Filter by **Exceeded limit**.</span></span> <span data-ttu-id="7bcd9-301">Sélectionnez \*\*True \*\* pour appliquer le filtre.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-301">Select **True** to enforce the filter.</span></span>

![Filtrage par limite dépassée.](../media/Reskit_2012_Tools_Documentation_Image13.jpg)

<span data-ttu-id="7bcd9-303">Filtrage sur **Critical levels (Niveaux critiques)**.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-303">Filter by **Critical levels**.</span></span> <span data-ttu-id="7bcd9-304">Sélectionnez **True** pour appliquer le filtre.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-304">Select **True** to enforce the filter.</span></span>

![Filtrage par niveaux critiques.](../media/Reskit_2012_Tools_Documentation_Image14.jpg)

<span data-ttu-id="7bcd9-306">Filtrage sur **Under utilized (Sous-utilisé)**.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-306">Filter by **Under utilized**.</span></span> <span data-ttu-id="7bcd9-307">Sélectionnez **True** pour appliquer le filtre.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-307">Select **True** to enforce the filter.</span></span>

![Filtrage en sous utilisé.](../media/Reskit_2012_Tools_Documentation_Image15.jpg)

<span data-ttu-id="7bcd9-309">Filtrage sur **Link Type (Type de liaison)**.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-309">Filter by **Link Type**.</span></span> <span data-ttu-id="7bcd9-310">Sélectionnez le ou les types devant être affichés.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-310">Select the type or types that need to be displayed.</span></span>

![Filtrage par type de lien.](../media/Reskit_2012_Tools_Documentation_Image16.jpg)

<span data-ttu-id="7bcd9-312">Filtrage sur **Region (Région)**.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-312">Filter by **Region**.</span></span> <span data-ttu-id="7bcd9-313">Sélectionnez la liste des régions pour lesquelles afficher les liaisons.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-313">Select a list of regions whose links need to be displayed.</span></span>

![Filtrage par région.](../media/Reskit_2012_Tools_Documentation_Image17.jpg)

### <a name="requirements"></a><span data-ttu-id="7bcd9-315">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="7bcd9-315">Requirements</span></span>

- <span data-ttu-id="7bcd9-316">.NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="7bcd9-316">The .NET Framework 3.5</span></span>

- <span data-ttu-id="7bcd9-317">Microsoft Excel 2010 ou Excel 2007</span><span class="sxs-lookup"><span data-stu-id="7bcd9-317">Microsoft Excel 2010 or Excel 2007</span></span>

### <a name="summary"></a><span data-ttu-id="7bcd9-318">Résumé</span><span class="sxs-lookup"><span data-stu-id="7bcd9-318">Summary</span></span>

<span data-ttu-id="7bcd9-p130">Bandwidth Utilization Analyzer permet de représenter l’utilisation de la bande passante audio pour le trafic des communications unifiées dans le réseau. Il permet également de créer des rapports sur l’utilisation de la bande passante vidéo dans le réseau.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-p130">Bandwidth Utilization Analyzer is used to plot the audio bandwidth utilization for UC traffic across the network. This tool can be used to report the utilization of video bandwidth on the network as well.</span></span>

## <a name="call-parkometer"></a><span data-ttu-id="7bcd9-321">Call Parkometer</span><span class="sxs-lookup"><span data-stu-id="7bcd9-321">Call Parkometer</span></span>
<span data-ttu-id="7bcd9-322"><a name="callpark"> </a></span><span class="sxs-lookup"><span data-stu-id="7bcd9-322"></span></span>

<span data-ttu-id="7bcd9-323">L’application en ligne de commande Call Parkometer permet d’accéder facilement à la base de données des orbites de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-323">Call Parkometer is a command-line application that provides easy access to the Call Park orbit database.</span></span>

### <a name="description"></a><span data-ttu-id="7bcd9-324">Description</span><span class="sxs-lookup"><span data-stu-id="7bcd9-324">Description</span></span>

<span data-ttu-id="7bcd9-325">L’outil Call Parkometer permet de suivre les appels actuellement parqués.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-325">Call Parkometer is a tool to track currently parked calls.</span></span> <span data-ttu-id="7bcd9-326">Il collecte également des statistiques sur les orbites et l’utilisation du serveur de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-326">It also collects statistics about orbits and Call Park Server (CPS) usage.</span></span> <span data-ttu-id="7bcd9-327">Cet outil de ligne de commande fournit les deux accès en lecture et en écriture à la base de données SQL Server de CPS orbite à partir d’un ordinateur connecté localement ou distant.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-327">This command-line tool provides both read and write-access to the CPS orbit SQL Server database from a local or remotely connected computer.</span></span>

<span data-ttu-id="7bcd9-328">Toutes les options s’excluent mutuellement.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-328">All options are mutually exclusive.</span></span> <span data-ttu-id="7bcd9-329">La syntaxe suivante est appliquée à la ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="7bcd9-329">Command-line syntax is as follows:</span></span>

- <span data-ttu-id="7bcd9-330">paramètre **-o** : répertorie toutes les plages d’orbites configurées pour ce pool.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-330">**-o** parameter—lists all orbit ranges configured for this pool.</span></span>

- <span data-ttu-id="7bcd9-331">paramètre **-n** : affiche la liste des orbites actuellement utilisées dans ce pool.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-331">**-n** parameter—lists all currently used orbits in this pool.</span></span> <span data-ttu-id="7bcd9-332">Les informations suivantes sont affichées :</span><span class="sxs-lookup"><span data-stu-id="7bcd9-332">The information displayed is as follows:</span></span>

  - <span data-ttu-id="7bcd9-333">URI (Uniform Resource Identifier) SIP du parqué et du parqueur.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-333">SIP Uniform Resource Identifier (URI) of the parkee and parker.</span></span>

  - <span data-ttu-id="7bcd9-334">Nom d’hôte du serveur de parcage d’appel sur lequel l’appel est parqué.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-334">Host name of the CPS where the call is parked.</span></span>

  - <span data-ttu-id="7bcd9-335">Date/heure du parcage de l’appel.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-335">Time stamp of when the call was parked.</span></span>

- <span data-ttu-id="7bcd9-336">paramètre **-f** : indique le nombre d’orbites disponibles actuellement dans la liste.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-336">**-f** parameter—lists the number of currently free orbits in the pool.</span></span>

- <span data-ttu-id="7bcd9-337">**paramètre- \<r\> n** : répertorie \<les\> n derniers appels en stationnement.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-337">**-r \<n\>** parameter—lists the \<n\> last parked calls.</span></span> <span data-ttu-id="7bcd9-338">Les informations suivantes sont affichées :</span><span class="sxs-lookup"><span data-stu-id="7bcd9-338">The information displayed is as follows:</span></span>

  - <span data-ttu-id="7bcd9-339">URI SIP du parqué.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-339">Parkee SIP URI.</span></span>

  - <span data-ttu-id="7bcd9-340">URI SIP du parqueur.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-340">Parker SIP URI.</span></span>

  - <span data-ttu-id="7bcd9-341">Nom d’hôte du serveur de parcage d’appel sur lequel l’appel est parqué.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-341">Host name of the CPS where the call was parked.</span></span>

  - <span data-ttu-id="7bcd9-342">Date/heure de récupération ou d’abandon de l’appel.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-342">Time stamp of when the call was retrieved or dropped.</span></span>

- <span data-ttu-id="7bcd9-343">\*\*-t\<n\> \*\* paramètre-tests de réservation d’une orbite dans la base de données pour afficher la randomisation des numéros en orbites attribués.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-343">**-t\<n\>** parameter - tests reserving an orbit in the database to show the randomness of the assigned orbit numbers.</span></span>

### <a name="output"></a><span data-ttu-id="7bcd9-344">Sortie</span><span class="sxs-lookup"><span data-stu-id="7bcd9-344">Output</span></span>

<span data-ttu-id="7bcd9-345">Selon les paramètres d’entrée spécifiés dans l’invite de commandes, l’outil Call Parkometer affiche la sortie suivante :</span><span class="sxs-lookup"><span data-stu-id="7bcd9-345">Depending on the input parameters that are specified at a command prompt, Call Parkometer displays the following output:</span></span>

- <span data-ttu-id="7bcd9-346">plages d’orbites configurées pour ce pool ;</span><span class="sxs-lookup"><span data-stu-id="7bcd9-346">All orbit ranges that are configured for this pool</span></span>

- <span data-ttu-id="7bcd9-347">appels actuellement parqués ;</span><span class="sxs-lookup"><span data-stu-id="7bcd9-347">Currently parked calls</span></span>

- <span data-ttu-id="7bcd9-348">nombre d’orbites libres (disponibles) ;</span><span class="sxs-lookup"><span data-stu-id="7bcd9-348">Number of free (available) orbits</span></span>

- <span data-ttu-id="7bcd9-349">appels parqués récemment ;</span><span class="sxs-lookup"><span data-stu-id="7bcd9-349">Recently parked calls</span></span>

- <span data-ttu-id="7bcd9-350">orbites réservées pour le test des valeurs d’orbite uniformes et aléatoires.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-350">Reserved orbits for testing uniform and random orbit values</span></span>

### <a name="purpose"></a><span data-ttu-id="7bcd9-351">Objectif</span><span class="sxs-lookup"><span data-stu-id="7bcd9-351">Purpose</span></span>

<span data-ttu-id="7bcd9-p135">L’outil CPS vie à fournir un accès par ligne de commande à la base de données du serveur de parcage d’appel. L’administrateur peut consulter l’utilisation du serveur de parcage d’appel et déterminer le nombre d’orbites affectées à un pool.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-p135">The purpose of the CPS tool is to provide command-line access to the CPS database. The administrator can view the CPS usage and determine the number of orbits assigned to a pool.</span></span>

### <a name="requirements"></a><span data-ttu-id="7bcd9-354">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="7bcd9-354">Requirements</span></span>

<span data-ttu-id="7bcd9-355">Aucune configuration n’est requise si cet outil est exécuté sur l’ordinateur qui exécute le serveur de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-355">There are no requirements if this tool is run on the same computer that is running CPS.</span></span> <span data-ttu-id="7bcd9-356">Si cet outil est exécuté sur un ordinateur distant, la base de données SQL Server utilisée par Skype entreprise Server 2015 doit être configurée pour autoriser l’accès à distance.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-356">If this tool is run on a remote computer, the SQL Server database used by Skype for Business Server 2015 must be configured to allow remote access.</span></span> <span data-ttu-id="7bcd9-357">L’appel de Parkometer doit être configuré à l’aide d’une chaîne de connexion de base de données SQL Server pour se connecter au serveur SQL Server du pool.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-357">Call Parkometer must be configured with a SQL Server database connection string to connect to the pool's SQL Server.</span></span> <span data-ttu-id="7bcd9-358">Cette chaîne de connexion de base de données SQL Server est définie dans le fichier de configuration **parkometer. exe. config**. Il doit être placé dans le même répertoire que parkometer. exe.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-358">This SQL Server database connection string is defined in the configuration file, **parkometer.exe.config**. It must be placed in the same directory where parkometer.exe is located.</span></span> <span data-ttu-id="7bcd9-359">Le fichier XML suivant est un exemple de parkometer. exe. config. Les paramètres qui doivent être configurés sont nom d’utilisateur (par exemple, mydomain\Administrator), mot de passe (par exemple, de monmotdepasse) et nom d’hôte (par exemple, MyServer).</span><span class="sxs-lookup"><span data-stu-id="7bcd9-359">The following XML file is an example of a parkometer.exe.config. The parameters that must be configured are user name (for example, mydomain\Administrator), password (for example, mypassword), and host name (for example, myserver).</span></span>

```xml
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

### <a name="examples"></a><span data-ttu-id="7bcd9-360">Exemples</span><span class="sxs-lookup"><span data-stu-id="7bcd9-360">Examples</span></span>

<span data-ttu-id="7bcd9-361">Plages d’orbites déployées : le paramètre-o répertorie toutes les plages d’orbites configurées pour ce pool comme illustré</span><span class="sxs-lookup"><span data-stu-id="7bcd9-361">Deployed orbit ranges: the -o parameter lists all orbit ranges that are configured for this pool as shown</span></span>

![Plages orbites dans Parkometer d’appel.](../media/Reskit_2012_Tools_Documentation_Image18.jpg)

<span data-ttu-id="7bcd9-363">Appels actuellement en cours : le paramètre-n recense tous les orbites actuellement utilisées sur ce pool, comme illustré ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-363">Currently parked calls: the -n parameter lists all currently used orbits on this pool as shown</span></span>

![Appels actuellement en cours d’appel dans Parkometer.](../media/Reskit_2012_Tools_Documentation_Image19.jpg)

<span data-ttu-id="7bcd9-365">Nombre d’orbites gratuites : le paramètre-f indique le nombre d’orbites libres actuellement dans le pool, comme illustré ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-365">Number of free orbits: the -f parameter lists the number of currently free orbits in the pool as shown</span></span>

![Orbites libres dans Parkometer d’appel.](../media/Reskit_2012_Tools_Documentation_Image20.jpg)

<span data-ttu-id="7bcd9-367">Appels récemment mis en garde : le paramètre \<-\> r n \<recense\> les n derniers appels parqués, comme illustré ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-367">Recently parked calls: the -r \<n\> parameter lists the \<n\> last parked calls as shown</span></span>

![Appels récemment dans le Parkometer.](../media/Reskit_2012_Tools_Documentation_Image21.jpg)

<span data-ttu-id="7bcd9-369">Test de réservation orbite : les \<tests\> de paramètre-t n servent à réapprovisionner une orbite dans la base de données, comme illustré ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-369">Test orbit reservation: the -t \<n\> parameter tests reserving an orbit in the database as shown</span></span>

![Testez les réservations orbites dans l’appel Parkometer.](../media/Reskit_2012_Tools_Documentation_Image22.jpg)

### <a name="summary"></a><span data-ttu-id="7bcd9-371">Résumé</span><span class="sxs-lookup"><span data-stu-id="7bcd9-371">Summary</span></span>

<span data-ttu-id="7bcd9-372">L’outil en ligne de commande Call Parkometer fournit des informations détaillées sur le serveur de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-372">Call Parkometer is a command-line tool that provides detailed information about the Call Park Server.</span></span>

## <a name="dbanalyze"></a><span data-ttu-id="7bcd9-373">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="7bcd9-373">DBAnalyze</span></span>
<span data-ttu-id="7bcd9-374"><a name="dba"> </a></span><span class="sxs-lookup"><span data-stu-id="7bcd9-374"></span></span>

### <a name="description"></a><span data-ttu-id="7bcd9-375">Description</span><span class="sxs-lookup"><span data-stu-id="7bcd9-375">Description</span></span>

<span data-ttu-id="7bcd9-376">DBAnalyze est un outil de ligne de commande qui permet aux administrateurs de collecter des rapports d’analyse sur les bases de données 2015 de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-376">DBAnalyze is a command-line tool that helps administrators to gather analysis reports about the Skype for Business Server 2015 databases.</span></span> <span data-ttu-id="7bcd9-377">DBAnalyze inclut les modes suivants : diagnostic, données des utilisateurs, conférence, unités de contrôle multipoint et fragmentation des disques :</span><span class="sxs-lookup"><span data-stu-id="7bcd9-377">DBAnalyze has the following modes: diagnostic, user data, conference, MCUs, and disk fragmentation:</span></span>

- <span data-ttu-id="7bcd9-378">**Mode diagnostic** Crée un rapport qui inclut des informations sur les tables (nombre d’enregistrements, fragmentation, taille des données et taille d’index), les données et la taille des fichiers journaux, la dernière période de sauvegarde, le nombre de contacts avec les serveurs qui exécutent Microsoft Office Communications Server, le nombre moyen d’autorisations, de contacts, de conteneurs, d’abonnements, de points de terminaison, de points de terminaison par utilisateur, d’utilisateurs incorrectement hébergés et la version de la base de données.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-378">**Diagnostic mode** Creates a report that includes information about tables (number of records, fragmentation, data size, and index size), data and log file sizes, the last back-up time, contact distribution among servers that are running Microsoft Office Communications Server, the average number of permissions, contacts, containers, subscriptions, publications, endpoints per user, any improperly homed users, users that can't be routed, the average number of conferences organized per user, scheduled conferences, active conferences, and the database version.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7bcd9-379">L’exécution du mode Diagnostic peut affecter les performances des serveurs.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-379">Running diagnostic mode can affect server performance.</span></span>

- <span data-ttu-id="7bcd9-380">**Mode données utilisateur** Signale les données de contact, de conteneur, d’abonnement, de composition, d’autorisation et de groupe de contacts pour un utilisateur spécifié ou pour les utilisateurs qui disposent de cet utilisateur dans leurs listes de contacts et d’autorisations.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-380">**User data mode** Reports contact, container, subscription, publication, permission, and contact-group data for a specified user or for users who have that user in their contact and permission lists.</span></span> <span data-ttu-id="7bcd9-381">Ce mode transmet également des données résumées sur les conférences organisées par un utilisateur ou auxquelles il est invité.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-381">This mode also reports summary data for conferences that a user organizes or is invited to.</span></span>

- <span data-ttu-id="7bcd9-382">**Mode conférence** Rapporte des données détaillées pour une conférence spécifique, y compris tous les détails de l’horaire de la Conférence, la liste d’invités, la liste des types de médias autorisés pour la Conférence, les MCU actifs (unités de contrôle multipoint), la liste des participants actifs et l’état de signalisation de chaque participant.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-382">**Conference mode** Reports detailed data for a specific conference, including all schedule-time details for the conference, the invitee list, the list of media types allowed for the conference, active MCUs (multipoint control units), the active participant list, and each participant's signaling state.</span></span>

- <span data-ttu-id="7bcd9-383">**ID de réunion de décodage** Décode un ID de réunion RTC (réseau téléphonique commuté) qui est spécifié par le commutateur **/pstnid** , mais qui ne se connecte pas à l’extrémité dorsale pour obtenir des informations détaillées.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-383">**Decode Meeting ID** Decodes a public switched telephone network (PSTN) meeting ID that is specified by the **/pstnid** switch but does not connect to the back end for detailed information.</span></span>

- <span data-ttu-id="7bcd9-384">**Résoudre une conférence** Décode un ID de réunion RTC spécifié par le commutateur **/pstnid** et affiche des informations sur la Conférence indiquée par l’ID.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-384">**Resolve conference** Decodes a PSTN meeting ID that is specified by the **/pstnid** switch and displays information about the conference indicated by the ID.</span></span>

- <span data-ttu-id="7bcd9-385">**Mode MCU** Signale l’ID, le type de média, l’URL, le statut de pulsation, le chargement de la Conférence et le chargement du participant pour chaque MCU du pool.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-385">**MCUs mode** Reports the ID, media type, URL, heartbeat status, conference load, and participant load for each MCU in the pool.</span></span>

- <span data-ttu-id="7bcd9-386">**Mode de fragmentation de disque** Affiche l’état de fragmentation de tous les disques.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-386">**Disk fragmentation mode** Displays the fragmentation status of all disks.</span></span>

<span data-ttu-id="7bcd9-p139">Cet outil permet de diagnostiquer plusieurs problèmes ou de planifier la capacité. Par exemple, si la plupart des utilisateurs hébergés sur un serveur A définissent des utilisateurs hébergés sur le serveur B comme contacts, l’administrateur peut déplacer les utilisateurs du serveur A vers le serveur B afin de réduire le trafic entre les serveurs.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-p139">This tool can be used to diagnose various problems or to assist administrators with capacity planning. For example, if most of the users homed on server A choose users homed on server B as their contacts, the administrator can move the users on server A to server B to reduce cross-server traffic.</span></span>

### <a name="output"></a><span data-ttu-id="7bcd9-389">Sortie</span><span class="sxs-lookup"><span data-stu-id="7bcd9-389">Output</span></span>

<span data-ttu-id="7bcd9-390">Cet outil génère des rapports prédéfinis sur la base de données 2015 de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-390">This tool outputs predefined reports about the Skype for Business Server 2015 database.</span></span> <span data-ttu-id="7bcd9-391">**Chemin**:%ProgramFiles%\Skype pour Business Server 2015 \ reskit</span><span class="sxs-lookup"><span data-stu-id="7bcd9-391">**Path**: %ProgramFiles%\Skype for Business Server 2015\Reskit</span></span>

### <a name="purpose"></a><span data-ttu-id="7bcd9-392">Objectif</span><span class="sxs-lookup"><span data-stu-id="7bcd9-392">Purpose</span></span>

<span data-ttu-id="7bcd9-393">Pour installer DbAnalyze. exe, copiez-le dans un dossier local, puis exécutez l’outil.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-393">To install Dbanalyze.exe, copy it to a local folder and then run the tool.</span></span> <span data-ttu-id="7bcd9-394">Pour utiliser l’outil, exécutez la commande suivante à partir de la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-394">To use the tool, run the following command from the command line.</span></span> <span data-ttu-id="7bcd9-395">`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`Les descriptions des options de la ligne de commande sont décrites ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-395">`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` The descriptions for the command-line options are shown below.</span></span>

![Options de ligne de commande pour DbAnalyze. exe.](../media/Reskit_2012_Tools_Documentation_Image35.JPG)

### <a name="requirements"></a><span data-ttu-id="7bcd9-397">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="7bcd9-397">Requirements</span></span>

 <span data-ttu-id="7bcd9-398">**Ordinateur** DBAnalyze ne peut être exécuté qu’à partir d’un ordinateur appartenant à un domaine sur lequel Skype entreprise Server 2015 est installé.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-398">**Computer** DBAnalyze can be run only from a domain-joined computer that has Skype for Business Server 2015 installed.</span></span>

 <span data-ttu-id="7bcd9-399">**Réseau** L’ordinateur doit pouvoir se connecter à la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-399">**Network** The computer should be able to connect to the back-end database.</span></span>

 <span data-ttu-id="7bcd9-400">Le **logiciel** ; Les composants logiciels de Skype entreprise Server 2015 doivent être installés avant d’exécuter DBAnalyze.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-400">**Software** Skype for Business Server 2015 software components must be installed before running DBAnalyze.</span></span>

 <span data-ttu-id="7bcd9-401">**Utilisateurs** Le tableau ci-dessous indique les administrateurs disposant des autorisations nécessaires pour accéder aux bases de données Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-401">**Users**The table below shows the administrators who have the necessary permissions to access Skype for Business Server 2015 databases.</span></span>

![Tableau des autorisations pour DbAnalyze. exe.](../media/Reskit_2012_Tools_Documentation_Image36.JPG)

> [!NOTE]
> <span data-ttu-id="7bcd9-403">Un compte d’administrateur local est nécessaire pour le mode **/report:disk**.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-403">A local administrator account is required for **/report:disk** mode.</span></span>

### <a name="examples"></a><span data-ttu-id="7bcd9-404">Exemples</span><span class="sxs-lookup"><span data-stu-id="7bcd9-404">Examples</span></span>

<span data-ttu-id="7bcd9-405">Les exemples suivants constituent des commandes Dbanalyze.exe correctes :</span><span class="sxs-lookup"><span data-stu-id="7bcd9-405">The following are examples of valid Dbanalyze.exe commands:</span></span>

```
dbanalyze.exe /report:diag
dbanalyze.exe /report:user /user:usera@domainb.com
dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
dbanalyze.exe /report:resolve /pstnid:12345
dbanalyze.exe /report:mcus
dbanalyze.exe /report:disk
```

### <a name="summary"></a><span data-ttu-id="7bcd9-406">Résumé</span><span class="sxs-lookup"><span data-stu-id="7bcd9-406">Summary</span></span>

<span data-ttu-id="7bcd9-407">DBAnalyzer permet aux administrateurs d’analyser rapidement et facilement les bases de données Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-407">DBAnalyzer provides administrators a quick and easy to analyze Skype for Business Server 2015 databases.</span></span>

## <a name="import-storage-service-data"></a><span data-ttu-id="7bcd9-408">Import Storage Service Data</span><span class="sxs-lookup"><span data-stu-id="7bcd9-408">Import Storage Service Data</span></span>
<span data-ttu-id="7bcd9-409"><a name="Issd"> </a></span><span class="sxs-lookup"><span data-stu-id="7bcd9-409"></span></span>

<span data-ttu-id="7bcd9-410">L’outil de kit de ressources ImportStorageServiceData permet de réimporter les données de file d’attente et de point de terminaison éliminées du service de stockage Lync Server dans le service de stockage.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-410">The ImportStorageServiceData resource kit tool allows for re-importing Queue and Endpoint data that was flushed out of the Storage Service (LYSS) back into the Storage Service.</span></span>

### <a name="description"></a><span data-ttu-id="7bcd9-411">Description</span><span class="sxs-lookup"><span data-stu-id="7bcd9-411">Description</span></span>

<span data-ttu-id="7bcd9-412">L’élimination de données du service de stockage peut être automatique (périodique) selon le statut des éléments de file d’attente ou la taille de la base de données.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-412">The data flushed out of the Storage Service could have been automatic (periodic) based on Queue Item status or database size.</span></span> <span data-ttu-id="7bcd9-413">Elle peut survenir suite à l’invocation manuelle de l’applet de commande de basculement du pool ou StorageServiceFullFlush (invoquée par l’applet de commande de basculement du pool).</span><span class="sxs-lookup"><span data-stu-id="7bcd9-413">It could have happened due to the manual invocation of the pool failover cmdlet, or the StorageServiceFullFlush cmdlet (which the pool failover cmdlet invokes).</span></span> <span data-ttu-id="7bcd9-414">Notez que les données ne peuvent pas être réimportées si la taille de la base de données du service de stockage (LYSS) au premier plan se trouve au-dessus du niveau normal, car cela risque de provoquer une exportation supplémentaire de données. De plus, tous les problèmes susceptibles d’avoir contribué à des erreurs qui entraînaient l’augmentation de la file d’attente du service de stockage doivent être résolus (par exemple, des erreurs de point de terminaison Exchange, des problèmes de réseau ou d’autres problèmes).</span><span class="sxs-lookup"><span data-stu-id="7bcd9-414">Note that data should ideally not be re-imported if any of the Storage Service (LYSS ) database size on the front ends is above the normal level, because doing so will likely just cause more data to be exported back out. Furthermore, any problems which could have contributed to errors that caused the Storage Service Queue to grow should first be resolved (for example Exchange endpoint errors, network issues, or other problems).</span></span>

 <span data-ttu-id="7bcd9-415">**Scénario 1 :** lors du basculement du pool, les fichiers peuvent être éliminés du service de stockage de chaque serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-415">**Scenario 1:** during pool failover, files may be flushed out from storage service for each front end.</span></span> <span data-ttu-id="7bcd9-416">Une fois le basculement terminé, l’outil doit être exécuté pour réimporter les données.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-416">After failover is completed, the tool should be run to re-import the data.</span></span>

 <span data-ttu-id="7bcd9-417">**Scénario 2 :** les données sont éliminées automatiquement chaque jour ou suite au dépassement de certains seuils de taille par la base de données du service de stockage (par exemple, 60 %, 80 %, 90 % de remplissage).</span><span class="sxs-lookup"><span data-stu-id="7bcd9-417">**Scenario 2:** data is being flushed automatically each day or in response to Storage Service database exceeding certain size thresholds ( for example 60%, 80%, 90% full ).</span></span> <span data-ttu-id="7bcd9-418">Ces données éliminées automatiquement doivent être régulièrement réimportées par l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-418">This automatically flushed data should be re-imported routinely by the administrator.</span></span> <span data-ttu-id="7bcd9-419">Dans le cas ci-dessus, si le module de contrôle SCOM n’est pas déployé, il existe des événements pour le service de stockage Skype entreprise Server relatifs aux données vidées du service de stockage.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-419">In the above situation, if the monitoring SCOM pack is not deployed, there are events for Skype for Business Server Storage Service relating to data being flushed from the Storage Service.</span></span> <span data-ttu-id="7bcd9-420">Les ID d’événement 32075 (démarrage du vidage complet), 32076 (fin du vidage complet), 32082 (démarrage du vidage de niveau maintenance), 32083 (fin du vidage de niveau maintenance), 32089 (vidage effectué à cause du remplissage de la base de données).</span><span class="sxs-lookup"><span data-stu-id="7bcd9-420">Event IDs of 32075 (full flush operation is started), 32076 (full flush has completed), 32082 (maintenance level flush started), 32083 (maintenance level flush complete), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="7bcd9-421">Notez que ces ID d’événement correspondent à la version finale.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-421">Note these event Ids correspond to the RTM release.</span></span> <span data-ttu-id="7bcd9-422">Lorsqu’un administrateur voit ces événements, cela signifie qu’il y a des fichiers qui ont été vidés. Ces données doivent être importées régulièrement à l’aide de cet outil, par exemple une fois par semaine.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-422">When an administrator sees these events, it means that there are files that have been flushed out. This data should routinely be imported back using this tool, for example once per week.</span></span>

<span data-ttu-id="7bcd9-423">Dans le cas de la version de service en ligne, si le Pack de gestion de l’intégrité pour Skype entreprise Server est déployé, de nouvelles alertes peuvent être déclenchées, ce qui demande à l’administrateur de réimporter les données vidées dans le service de stockage.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-423">For the Online Service release, if health monitoring SCOM pack for Skype for Business Server is deployed, there are new alerts which may be raised which ask the administrator to re-import the flushed data back into Storage Service.</span></span> <span data-ttu-id="7bcd9-424">Il y aura un événement correspondant dans le journal des événements sur le serveur frontal qui déclenchait l’alerte.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-424">There will be a corresponding event in the event log on the Front End server which triggered the alert.</span></span> <span data-ttu-id="7bcd9-425">L’événement fournit une description du chemin d’accès parent sous lequel se trouvent les fichiers de données vidées, ainsi que du nombre de fichiers qui répondent aux critères d’alerte.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-425">The event will give a description of the Parent path under which the flushed data files are located, as well as how many files there are which meet the alert criteria.</span></span> <span data-ttu-id="7bcd9-426">Le critère d’alerte est que le chemin d’accès parent est inférieur ou égal à X jours (où X et Y sont prédéfinis dans le StorageService, mais peut être substitué en modifiant le fichier APPCONFIG.) Vous trouverez ci-dessous deux exemples d’événements qui peuvent déclencher l’alerte d’intégrité, en étant leur chemin parent.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-426">The alert criteria is that there are X or more files under the particular parent path which are at least Y days old ( where X and Y are preset within the StorageService but can be overridden by changing the APPCONFIG file.)Two examples of events which can trigger the health alert are shown below, with the difference being their parent path.</span></span> <span data-ttu-id="7bcd9-427">Il existe une possibilité de partage de fichiers de service Web, tandis que l’autre est le répertoire de données d’application local de chaque frontal.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-427">One possibility is under Web service file share, while the other possibility is the local Application Data directory of each front end.</span></span> <span data-ttu-id="7bcd9-428">(par exemple, c:\ProgramData\Microsoft\Skype pour Business Server 2015 \ StorageService).</span><span class="sxs-lookup"><span data-stu-id="7bcd9-428">( for example c:\ProgramData\Microsoft\Skype for Business Server 2015\StorageService ).</span></span> <span data-ttu-id="7bcd9-429">L’administrateur doit alors exécuter cet outil reskit.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-429">The administrator will then run this reskit tool.</span></span>

<span data-ttu-id="7bcd9-430">Cet outil augmente la charge processeur et d’E/S sur le serveur frontal sur lequel il est exécuté, ainsi que sur les autre serveurs frontaux, si les données n’appartiennent pas au serveur frontal sur lequel l’outil est exécuté.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-430">This tool will increase CPU and IO load on the front end it is running on, as well as other front ends, in the situation that the data is not owned by the front end that the tool is executed on.</span></span> <span data-ttu-id="7bcd9-431">Il est recommandé d’exécuter cet outil lorsque les serveurs frontaux ne sont pas soumis à une charge processeur et d’E/S importante, par exemple en dehors des heures de pointe.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-431">We recommend runng this tool when front ends are not under heavy CPU and IO load, for example outside of peak hours.</span></span> <span data-ttu-id="7bcd9-432">Deuxièmement, cet outil peut prendre 2 à 3 minutes pour importer un fichier de données.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-432">Secondly, this tool can 2 to 3 minutes to import one data file.</span></span> <span data-ttu-id="7bcd9-433">Vous devez garder cette information à l’esprit lorsque vous cherchez à estimer le délai d’exécution de l’outil.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-433">Keep this in mind when estimating how long tool will be running.</span></span> <span data-ttu-id="7bcd9-434">Le fichier journal détaillé généré par l’outil apparaît par défaut dans le magasin de fichiers.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-434">The verbose log file generated by the tool will by default appear on the File Store.</span></span> <span data-ttu-id="7bcd9-435">Supprimez-le si aucune erreur n’est signalée, car la taille de celui-ci peut atteindre plusieurs Mo, voire davantage.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-435">Delete it if there are no errors reported, because the log file can be tens of MB or more.</span></span>

![Exemples de journaux d’événements du serveur de stockage.](../media/Reskit_2012_Tools_Documentation_Image1.jpg)

### <a name="requirements"></a><span data-ttu-id="7bcd9-437">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="7bcd9-437">Requirements</span></span>

<span data-ttu-id="7bcd9-438">Installez les outils du kit de ressources Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-438">Install the Skype for Business Server 2015 Resource Kit tools.</span></span> <span data-ttu-id="7bcd9-439">L’outil s’exécute sur les ordinateurs appartenant à un domaine pour lesquels Skype entreprise Server et Skype entreprise Server Management Shell sont installés.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-439">The tool runs on domain-joined machines where Skype for Business Server and Skype for Business Server Management Shell are installed.</span></span> <span data-ttu-id="7bcd9-440">L’outil utilise une cmdlet de Management Shell pour identifier tous les serveurs frontaux de la liste.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-440">The tool uses a cmdlet from the management shell to identify all the Front End servers in the pool.</span></span> <span data-ttu-id="7bcd9-441">Deuxièmement, l’outil doit être exécuté à partir d’un ordinateur du pool sur lequel la base de données **RtcLocal** est installée.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-441">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="7bcd9-442">Cette base de données est utilisée par l’outil pour récupérer l’emplacement du partage de fichiers WebService pour le pool.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-442">This database is used by the tool to retrieve the location of the WEBSERVICE file share for the pool.</span></span> <span data-ttu-id="7bcd9-443">Par ailleurs, avant d’utiliser l’outil, chaque serveur frontal doit d’abord activer l’accès distant Windows PowerShell à l’aide de **Enable-PSRemoting** sur chaque serveur frontal, ainsi que de l’ordinateur à partir duquel l’outil est exécuté.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-443">Additionally, before using the tool, each Front End server must first enable Windows PowerShell Remoting using **Enable-PSRemoting** on each Front End server, as well as the machine that the tool is executed from.</span></span> <span data-ttu-id="7bcd9-444">Dans le cas contraire, les commandes Windows PowerShell distantes de cet outil échoueront.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-444">Otherwise, remote Windows PowerShell commands from this tool will fail.</span></span> <span data-ttu-id="7bcd9-445">La fonctionnalité d’accès distant de Windows PowerShell peut être désactivée sur tous les serveurs frontaux de la liste une fois l’opération terminée.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-445">Windows PowerShell Remoting can be turned off on all Front End servers in the pool after it is finished.</span></span> <span data-ttu-id="7bcd9-446">Enfin, le compte ou les informations d’identification appelant l’outil doivent disposer d’autorisations en lecture/écriture sur le partage de fichiers WebPart pour le pool sur lequel ils exécutent cet outil.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-446">Finally, the account or credential invoking the tool must have read/write permission to the webservice file share for the pool they are executing this tool on.</span></span> <span data-ttu-id="7bcd9-447">Dans le cas contraire, l’outil échoue avec des erreurs d’autorisation d’e/s.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-447">Otherwise the tool will fail with IO Permission errors.</span></span>

> [!NOTE]
> <span data-ttu-id="7bcd9-448">Sur Windows Server 2012, la mise à niveau de Windows PowerShell est activée par défaut, mais pas sur le système d’exploitation Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-448">On Windows Server 2012, Windows PowerShell Remoting is enabled by default, but not on the Windows Server 2008 operating system.</span></span>

### <a name="examples"></a><span data-ttu-id="7bcd9-449">Exemples</span><span class="sxs-lookup"><span data-stu-id="7bcd9-449">Examples</span></span>

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

## <a name="lcssync"></a><span data-ttu-id="7bcd9-450">LCSSync</span><span class="sxs-lookup"><span data-stu-id="7bcd9-450">LCSSync</span></span>
<span data-ttu-id="7bcd9-451"><a name="LCSSync"> </a></span><span class="sxs-lookup"><span data-stu-id="7bcd9-451"></span></span>

<span data-ttu-id="7bcd9-452">L’outil LCSSync vous permet de déployer le logiciel de communications Skype entreprise Server 2015 dans un environnement multiforêt.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-452">The LCSSync tool helps to deploy Skype for Business Server 2015 communications software in a multi-forest environment.</span></span> <span data-ttu-id="7bcd9-453">Cet outil permet de synchroniser des utilisateurs et des groupes à partir de forêts utilisateur différentes en tant qu’objet de contact services de domaine Active Directory (AD FS) à une forêt centrale dans laquelle Skype entreprise Server 2015 est installé.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-453">This tool is used to synchronize users and groups from different user forests as an Active Directory Domain Services contact object to a central forest where Skype for Business Server 2015 is installed.</span></span>

### <a name="description"></a><span data-ttu-id="7bcd9-454">Description</span><span class="sxs-lookup"><span data-stu-id="7bcd9-454">Description</span></span>

 <span data-ttu-id="7bcd9-455">LCSSync utilise les objets de contact des services de domaine Active Directory synchronisés dans la forêt centrale pour permettre aux utilisateurs de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-455">LCSSync uses the synchronized Active Directory Domain Services contact objects in the central forest to enable users for Skype for Business Server.</span></span> <span data-ttu-id="7bcd9-456">Pour fournir une connexion unique, le compte d’utilisateur principal doit être mappé à l’objet de contact services de domaine Active Directory (AD FS) dans la forêt centrale de Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-456">To provide single sign-in, the primary user account must be mapped to the Active Directory Domain Services contact object in the central forest for Skype for Business Server 2015.</span></span> <span data-ttu-id="7bcd9-457">Cet outil aide à effectuer l’opération de mappage.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-457">This tool helps perform that mapping.</span></span> <span data-ttu-id="7bcd9-458">Il fournit des modèles pour la création des agents de gestion dans Microsoft Identity Integration Server.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-458">This tool provides templates for creating Management Agents in the Microsoft Identity Integration Server.</span></span>

### <a name="summary"></a><span data-ttu-id="7bcd9-459">Résumé</span><span class="sxs-lookup"><span data-stu-id="7bcd9-459">Summary</span></span>

<span data-ttu-id="7bcd9-460">L’outil LCSSync vous permet de déployer Skype entreprise Server 2015 dans un environnement multiforêt.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-460">The LCSSync tool helps to deploy Skype for Business Server 2015 in a multi-forest environment.</span></span>

## <a name="lookup-user-console"></a><span data-ttu-id="7bcd9-461">Lookup User Console</span><span class="sxs-lookup"><span data-stu-id="7bcd9-461">Lookup User Console</span></span>
<span data-ttu-id="7bcd9-462"><a name="LUC"> </a></span><span class="sxs-lookup"><span data-stu-id="7bcd9-462"></span></span>

<span data-ttu-id="7bcd9-463">L’outil LookupUserConsole affiche les informations de routage internes de Skype entreprise Server relatives aux utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-463">The LookupUserConsole tool displays internal Skype for Business Server routing information about specific users.</span></span> <span data-ttu-id="7bcd9-464">Ces informations peuvent être utiles au personnel du support technique Microsoft dans le cadre du diagnostic des problèmes de déploiement et de routage.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-464">This information may be useful to Microsoft support personal in diagnosing deployment and routing problems.</span></span>

### <a name="description"></a><span data-ttu-id="7bcd9-465">Description</span><span class="sxs-lookup"><span data-stu-id="7bcd9-465">Description</span></span>

 <span data-ttu-id="7bcd9-466">L’exécution de LookupUserConsole. exe entraîne l’ouverture d’une invite de commandes qui accepte les adresses SIP et tente d’afficher des informations de routage Skype entreprise Server internes associées.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-466">Executing LookupUserConsole.exe will open a command prompt that accepts SIP addresses and attempts to display internal Skype for Business Server routing information relating them.</span></span> <span data-ttu-id="7bcd9-467">Tapez **exit** pour quitter l’outil LookupUserConsole.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-467">Type **exit** to quit the LookupUserConsole tool.</span></span>

### <a name="requirements"></a><span data-ttu-id="7bcd9-468">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="7bcd9-468">Requirements</span></span>

<span data-ttu-id="7bcd9-469">Installez le kit de ressources de Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-469">Install the Skype for Business Server 2015 Resource Kit.</span></span> <span data-ttu-id="7bcd9-470">L’outil s’exécute sur les ordinateurs appartenant à un domaine sur lesquels Skype entreprise Server est installé.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-470">The tool runs on domain-joined machines where Skype for Business Server is installed.</span></span>

### <a name="examples"></a><span data-ttu-id="7bcd9-471">Exemples</span><span class="sxs-lookup"><span data-stu-id="7bcd9-471">Examples</span></span>

<span data-ttu-id="7bcd9-472">C:\Program Files\Skype pour Business Server 2015 \ reskit\>LookupUserConsole. exe</span><span class="sxs-lookup"><span data-stu-id="7bcd9-472">C:\Program Files\Skype for Business Server 2015\ResKit\>LookupUserConsole.exe</span></span>

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

## <a name="msturnping"></a><span data-ttu-id="7bcd9-473">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="7bcd9-473">MsTurnPing</span></span>
<span data-ttu-id="7bcd9-474"><a name="MsTurnPing"> </a></span><span class="sxs-lookup"><span data-stu-id="7bcd9-474"></span></span>

<span data-ttu-id="7bcd9-475">L’outil de MSTurnPing permet à un administrateur de Skype entreprise Server le logiciel de communication 2015 de vérifier l’état des serveurs exécutant les services d’authentification audio et vidéo et les serveurs qui exécutent des services de stratégie de bande passante dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-475">The MSTurnPing tool allows an administrator of Skype for Business Server 2015 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

### <a name="description"></a><span data-ttu-id="7bcd9-476">Description</span><span class="sxs-lookup"><span data-stu-id="7bcd9-476">Description</span></span>

<span data-ttu-id="7bcd9-477">L’outil de MSTurnPing permet à un administrateur de Skype entreprise Server le logiciel de communication 2015 de vérifier l’état des serveurs exécutant les services d’authentification audio et vidéo et les serveurs qui exécutent des services de stratégie de bande passante dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-477">The MSTurnPing tool allows an administrator of Skype for Business Server 2015 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

<span data-ttu-id="7bcd9-478">L’outil permet d’effectuer les tests suivants :</span><span class="sxs-lookup"><span data-stu-id="7bcd9-478">The tool allows the administrator to perform the following tests:</span></span>

1. <span data-ttu-id="7bcd9-479">Test des serveurs Edge A/V : l’outil effectue des tests sur tous les serveurs Edge A/V dans la topologie comme suit :</span><span class="sxs-lookup"><span data-stu-id="7bcd9-479">A/V Edge Server test: The tool performs tests against all A/V Edge Servers in the topology by doing the following:</span></span>

   - <span data-ttu-id="7bcd9-480">Vérifier que le service d’authentification audio/vidéo de Skype entreprise Server est démarré et peut fournir des informations d’identification appropriées.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-480">Verifying that the Skype for Business Server Audio/Video Authentication service is started and can issue proper credentials.</span></span>

   - <span data-ttu-id="7bcd9-481">Vérifier que le service Edge audio/vidéo de Skype entreprise Server est démarré et peut allouer correctement les ressources sur le bord externe.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-481">Verifying that the Skype for Business Server Audio/Video Edge service is started and can allocate the resources on the external edge successfully.</span></span>

2. <span data-ttu-id="7bcd9-482">Test des services de stratégie de bande passante : l’outil effectue des tests sur tous les serveurs exécutant les services de stratégie de bande passante dans la topologie comme suit :</span><span class="sxs-lookup"><span data-stu-id="7bcd9-482">Bandwidth Policy Service test: The tool performs tests against all the servers that are running the Bandwidth Policy Services in the topology by doing the following:</span></span>

   - <span data-ttu-id="7bcd9-483">Vérifier que le service de stratégie de bande passante de Skype entreprise Server (authentification) est démarré et peut émettre des informations d’identification appropriées.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-483">Verifying that the Skype for Business Server Bandwidth Policy Service (Authentication) is started and can issue proper credentials.</span></span>

   - <span data-ttu-id="7bcd9-484">Vérifiez que le service de stratégie de bande passante de Skype entreprise Server (cœur) est démarré et qu’il est possible d’effectuer le contrôle de bande passante.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-484">Verifying that the Skype for Business Server Bandwidth Policy Service (Core) is started and can perform the bandwidth check successfully.</span></span>

<span data-ttu-id="7bcd9-485">Cet outil doit être exécuté à partir d’un ordinateur qui fait partie de la topologie et sur lequel le magasin local est installé. </span><span class="sxs-lookup"><span data-stu-id="7bcd9-485">This tool must be run from a computer that is part of the topology and has the local store installed.</span></span>

### <a name="output"></a><span data-ttu-id="7bcd9-486">Sortie</span><span class="sxs-lookup"><span data-stu-id="7bcd9-486">Output</span></span>

<span data-ttu-id="7bcd9-487">L’outil génère des résultats pour chacune des opérations.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-487">The tool outputs the results of each of the operations.</span></span>

- <span data-ttu-id="7bcd9-488">Pour le test **AudioVideoEdgeServer**, l’outil génère les résultats suivants :</span><span class="sxs-lookup"><span data-stu-id="7bcd9-488">If the **AudioVideoEdgeServer** test is performed, the tool outputs are the following:</span></span>

  - <span data-ttu-id="7bcd9-489">Les résultats des tests sur les ordinateurs qui fournissent le service d’authentification audio/vidéo de Skype entreprise Server 2015 dans la topologie ;</span><span class="sxs-lookup"><span data-stu-id="7bcd9-489">The test results of the computers that provide the Skype for Business Server 2015 Audio/Video Authentication service in the topology</span></span>

  - <span data-ttu-id="7bcd9-490">Les résultats des tests pour les ordinateurs qui fournissent le service de périmètre audio/vidéo de Skype entreprise Server 2015 dans la topologie</span><span class="sxs-lookup"><span data-stu-id="7bcd9-490">The test results of the computers that provide the Skype for Business Server 2015 Audio/Video Edge service in the topology</span></span>

- <span data-ttu-id="7bcd9-491">Pour le test **BandwidthPolicyServer**, l’outil génère les résultats suivants :</span><span class="sxs-lookup"><span data-stu-id="7bcd9-491">If the **BandwidthPolicyServer** test is performed, the tool outputs are the following:</span></span>

  - <span data-ttu-id="7bcd9-492">Les résultats des tests sur les ordinateurs qui fournissent le service de stratégie de bande passante Skype entreprise Server 2015 (authentification) dans la topologie ;</span><span class="sxs-lookup"><span data-stu-id="7bcd9-492">The test results of the computers that provide the Skype for Business Server 2015 Bandwidth Policy Service (Authentication) in the topology</span></span>

  - <span data-ttu-id="7bcd9-493">Les résultats des tests sur les ordinateurs qui fournissent le service de stratégie de bande passante Skype entreprise Server 2015 (cœur) dans la topologie ;</span><span class="sxs-lookup"><span data-stu-id="7bcd9-493">The test results of the computers that provide the Skype for Business Server 2015 Bandwidth Policy Service (Core) in the topology</span></span>

### <a name="requirements"></a><span data-ttu-id="7bcd9-494">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="7bcd9-494">Requirements</span></span>

- <span data-ttu-id="7bcd9-495">Cet outil doit être exécuté à partir d’un ordinateur de la topologie sur lequel le magasin local est installé.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-495">This tool must be run from a computer that is in the topology and that has the local store.</span></span>

- <span data-ttu-id="7bcd9-496">L’outil doit être exécuté par un administrateur ayant accès au magasin local.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-496">The tool must be run as an administrator who has access to the local store.</span></span>

### <a name="examples"></a><span data-ttu-id="7bcd9-497">Exemples</span><span class="sxs-lookup"><span data-stu-id="7bcd9-497">Examples</span></span>

<span data-ttu-id="7bcd9-498">Voici un exemple de saisie pour l’outil.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-498">The following is an example of the tool input.</span></span>

```
MsTurnPing -ServerRole AudioVideoEdgeServer

MsTurnPing -ServerRole BandwidthPolicyServer
```

### <a name="summary"></a><span data-ttu-id="7bcd9-499">Résumé</span><span class="sxs-lookup"><span data-stu-id="7bcd9-499">Summary</span></span>

<span data-ttu-id="7bcd9-500">Cet outil peut être utile pour les administrateurs 2015 de Skype entreprise Server qui souhaitent vérifier l’état des serveurs qui exécutent les services audio/vidéo et de stratégie de bande passante.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-500">This tool can be a valuable resource to Skype for Business Server 2015 administrators who want to check the status of the servers that are running audio/video and bandwidth policy services.</span></span>

## <a name="network-configuration-viewer"></a><span data-ttu-id="7bcd9-501">Network Configuration Viewer</span><span class="sxs-lookup"><span data-stu-id="7bcd9-501">Network Configuration Viewer</span></span>
<span data-ttu-id="7bcd9-502"><a name="NCV"> </a></span><span class="sxs-lookup"><span data-stu-id="7bcd9-502"></span></span>

<span data-ttu-id="7bcd9-503">La visionneuse de configuration de réseau peut être utilisée par les administrateurs de logiciels de communication de Skype entreprise 2015 Server pour afficher la topologie du réseau de contrôle d’admission des appels (CAC) pour une entreprise mise en service pour autoriser les sessions de communication en temps réel, comme appels vocaux ou vidéo en fonction de la capacité de bande passante spécifiée.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-503">Network Configuration Viewer can be used by Skype for Business Server 2015 communications software administrators to view call admission control (CAC) network topology for an enterprise that is provisioned to allow real-time communication sessions, such as voice or video calls based on specified bandwidth capacity.</span></span> <span data-ttu-id="7bcd9-504">Les administrateurs 2015 de Skype entreprise Server définissent des stratégies CAC qui sont mises en œuvre par les services de stratégie de bande passante qui sont installés avec Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-504">Skype for Business Server 2015 administrators define CAC policies, which are enforced by the Bandwidth Policy services that are installed with Skype for Business Server 2015.</span></span>

### <a name="description"></a><span data-ttu-id="7bcd9-505">Description</span><span class="sxs-lookup"><span data-stu-id="7bcd9-505">Description</span></span>

<span data-ttu-id="7bcd9-506">Network Configuration Viewer (NetworkConfigurationViewer.exe) permet aux administrateurs d’effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="7bcd9-506">Network Configuration Viewer (NetworkConfigurationViewer.exe) allows administrators to perform the following tasks:</span></span>

- <span data-ttu-id="7bcd9-507">Chargez et affichez la topologie du réseau CAC à partir d’un déploiement 2015 de Skype entreprise Server dans un format graphique.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-507">Load and view CAC network topology from a Skype for Business Server 2015 deployment in a graphical format.</span></span>

- <span data-ttu-id="7bcd9-508">charger et afficher la topologie réseau de contrôle d’admission des appels à partir d‘un fichier journal de serveur de stratégie de bande passante dans un format graphique ;</span><span class="sxs-lookup"><span data-stu-id="7bcd9-508">Load and view CAC network topology from a Bandwidth Policy Server log file in a graphical format.</span></span>

- <span data-ttu-id="7bcd9-509">enregistrer et stocker la topologie réseau de contrôle d’admission des appels dans un format XML sur le disque ;</span><span class="sxs-lookup"><span data-stu-id="7bcd9-509">Save and store CAC network topology in an XML format on the disk.</span></span>

- <span data-ttu-id="7bcd9-510">enregistrer et stocker le diagramme de la topologie réseau de contrôle d’admission des appels au format JPG ou BMP ;</span><span class="sxs-lookup"><span data-stu-id="7bcd9-510">Save and store CAC network topology diagram in JPG or BMP format.</span></span>

- <span data-ttu-id="7bcd9-511">afficher les données de configuration de la topologie réseau de contrôle d’admission des appels ;</span><span class="sxs-lookup"><span data-stu-id="7bcd9-511">View CAC network topology configuration data.</span></span>

- <span data-ttu-id="7bcd9-512">afficher la topologie réseau de contrôle d’admission des appels dans une arborescence ;</span><span class="sxs-lookup"><span data-stu-id="7bcd9-512">View CAC network topology in a tree-view style.</span></span>

- <span data-ttu-id="7bcd9-513">définir des connecteurs personnalisés pour les liaisons de la topologie réseau de contrôle d’admission des appels (par exemple, liaisons site-région, région-région et site-site) ;</span><span class="sxs-lookup"><span data-stu-id="7bcd9-513">Define custom connectors for CAC network topology links (for example, site-to-region, region-to-region, and site-to-site links).</span></span>

- <span data-ttu-id="7bcd9-514">afficher les informations de site, informations de région, stratégies de bande passante et liaisons réseau approvisionnées de la topologie réseau de contrôle d’admission des appels.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-514">View CAC network topology site information, region Information, and provisioned bandwidth policies and network links.</span></span>

### <a name="purpose"></a><span data-ttu-id="7bcd9-515">Objectif</span><span class="sxs-lookup"><span data-stu-id="7bcd9-515">Purpose</span></span>

<span data-ttu-id="7bcd9-516">Afficher les liaisons de la topologie réseau de contrôle d’admission des appels dans une interface graphique.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-516">View enterprise CAC network topology links in a graphical interface.</span></span>

### <a name="examples"></a><span data-ttu-id="7bcd9-517">Exemples</span><span class="sxs-lookup"><span data-stu-id="7bcd9-517">Examples</span></span>

 <span data-ttu-id="7bcd9-518">**Charger et afficher la topologie du réseau CAC à partir d’un déploiement 2015 de Skype entreprise Server sous forme graphique**: les administrateurs 2015 de Skype entreprise Server peuvent charger et afficher la configuration de topologie du réseau CAC sur n’importe quel ordinateur Skype entreprise Server 2015 en utilisant l’option **Télécharger la configuration réseau** , comme illustré dans la figure ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-518">**Load and view CAC network topology from a Skype for Business Server 2015 deployment in a graphical format**: Skype for Business Server 2015 administrators can load and view CAC network topology configuration on any Skype for Business Server 2015 computer by using the **Download Network Configuration** option as shown in the figure below.</span></span> <span data-ttu-id="7bcd9-519">L’outil ne parvient pas à télécharger ou à afficher une configuration de ce type lors de son déploiement sur un ordinateur qui n’est pas connecté au magasin de configuration de Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-519">The tool will fail to download or view such a configuration when deployed on a computer that does not have connectivity to the Skype for Business Server 2015 configuration store.</span></span>

![Téléchargement de la configuration réseau.](../media/Reskit_2012_Tools_Documentation_Image23.jpg)

 <span data-ttu-id="7bcd9-521">**Chargez et affichez la topologie de réseau CAC à partir d’un fichier journal du serveur de stratégie de bande passante dans un format graphique :** Les serveurs de stratégies de bande passante de Skype entreprise Server 2015 enregistrent la topologie du réseau CAC dans le cadre du mécanisme de journalisation de l’emplacement du partage de fichiers Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-521">**Load and View CAC network topology from a Bandwidth Policy server log file in a graphical format:** Skype for Business Server 2015 Bandwidth Policy servers save the CAC network topology as a part of the logging mechanism under the Skype for Business Server 2015 file share location.</span></span> <span data-ttu-id="7bcd9-522">Les administrateurs 2015 de Skype entreprise Server peuvent afficher ce type de fichier dans un format graphique à l’aide de l’option **ouvrir la configuration réseau** , comme illustré ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-522">Skype for Business Server 2015 administrators can view such a file in a graphical format by using the **Open Network Configuration** option as shown below.</span></span>

![Ouverture d’un fichier journal du serveur de stratégie de bande passante.](../media/Reskit_2012_Tools_Documentation_Image24.jpg)

<span data-ttu-id="7bcd9-524">Enregistrez et stockez la topologie de réseau CAC au format XML sur le disque : les administrateurs 2015 de Skype entreprise Server peuvent enregistrer le fichier de configuration de topologie de réseau CAC au format XML en utilisant l’option **enregistrer une copie de la configuration réseau** , comme illustré ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-524">Save and store CAC network topology in an XML format on the disk: Skype for Business Server 2015 administrators can save the CAC network topology configuration file in an XML format by using the **Save a copy of Network Configuration** option as shown below.</span></span> <span data-ttu-id="7bcd9-525">Le fichier de configuration enregistré peut ensuite être utilisé en mode hors connexion à des fins d’affichage graphique.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-525">The saved configuration file can then be used offline for graphical viewing purposes.</span></span>

![Enregistrez la configuration réseau sous forme de fichier XML.](../media/Reskit_2012_Tools_Documentation_Image25.jpg)

<span data-ttu-id="7bcd9-527">Enregistrez et enregistrez le diagramme de topologie du réseau CAC au format JPG ou BMP : les administrateurs 2015 de Skype entreprise Server peuvent enregistrer la configuration de topologie du réseau CAC dans des formats de fichiers JPG et BMP en utilisant l’option **enregistrer le diagramme de configuration réseau en tant qu’image** , comme illustré ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-527">Save and Store CAC network topology diagram in JPG or BMP format: Skype for Business Server 2015 administrators can save the CAC network topology configuration in a graphical format (JPG and BMP file formats) by using the **Save Network Configuration diagram as picture** option as shown below.</span></span>

![Enregistrez la configuration réseau en tant qu’image.](../media/Reskit_2012_Tools_Documentation_Image26.jpg)

 <span data-ttu-id="7bcd9-529"><strong>Afficher les données de configuration de la topologie du réseau CAC :</strong> Les administrateurs 2015 de Skype entreprise Server peuvent afficher les données de configuration du réseau associées, telles que les zones du réseau, les sites réseau, les profils de bande passante et les adresses IP de sous-réseau dans un format de texte à l’aide de l’option Afficher les données de configuration réseau, comme illustré ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-529"><strong>View CAC network topology configuration data:</strong>Skype for Business Server 2015 administrators can view related network configuration data such as network regions, network sites, bandwidth profiles, and site subnet IP addresses in a textual format by using the View Network Configuration data option as shown below.</span></span>

![Affichage des données de configuration du réseau.](../media/Reskit_2012_Tools_Documentation_Image27.jpg)

 <span data-ttu-id="7bcd9-531">**Voir la topologie du réseau CAC dans un style d’arborescence :** Les administrateurs 2015 de Skype entreprise Server peuvent afficher les données de configuration du réseau associées dans un style d’affichage d’arborescence graphique à l’aide du panneau de configuration sur le côté gauche de la fenêtre d’outils, comme illustré ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-531">**View CAC network topology in a tree-view style:** Skype for Business Server 2015 administrators can view related network configuration data in a graphical tree view style by using the control panel on the left side of the tool window as shown below.</span></span>

![Afficher les données de configuration du réseau dans une arborescence.](../media/Reskit_2012_Tools_Documentation_Image28.jpg)

 <span data-ttu-id="7bcd9-533">**Définissez des connecteurs personnalisés pour les liens de topologie de réseau CAC (par exemple, les liens de site à zone, de région à zone et de site à site) :** Les administrateurs 2015 de Skype entreprise Server peuvent définir des connecteurs graphiques personnalisés pour les liaisons réseau WAN de configuration réseau CAC en utilisant l’option paramètres, comme illustré ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-533">**Define custom connectors for CAC network topology links (such as site-to-region, region-to-region, and site-to-site links):** Skype for Business Server 2015 administrators can define custom graphical connectors for CAC network configuration WAN links by using the Settings option as shown below.</span></span> <span data-ttu-id="7bcd9-534">Ceci permet de différencier divers types de liaisons réseau approvisionnées dans la configuration du réseau.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-534">This helps differentiate between various types of network links that are provisioned in the network configuration.</span></span>

![Utilitaires](../media/Reskit_2012_Tools_Documentation_Image29.jpg)

 <span data-ttu-id="7bcd9-536">**Affichez les informations de site et les stratégies de bande passante approvisionnées du réseau CAC.** Les administrateurs 2015 de Skype entreprise Server peuvent afficher les informations relatives à la région du réseau CAC, les informations du site et les informations de configuration de la bande passante CAC en utilisant les options indiquées ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-536">**View CAC network topology site information, region information, and provisioned bandwidth policies:** Skype for Business Server 2015 administrators can view related CAC network region information, site information, and CAC bandwidth provisioning information by using options shown below.</span></span> <span data-ttu-id="7bcd9-537">(Par exemple, cliquez sur **informations** dans une région réseau ou un objet de site réseau.)</span><span class="sxs-lookup"><span data-stu-id="7bcd9-537">(For example, click **Info** in a network region or network site object.)</span></span>

![Définition de connecteurs personnalisés pour votre réseau.](../media/Reskit_2012_Tools_Documentation_Image30.jpg)

### <a name="summary"></a><span data-ttu-id="7bcd9-539">Résumé</span><span class="sxs-lookup"><span data-stu-id="7bcd9-539">Summary</span></span>

<span data-ttu-id="7bcd9-540">Cet outil peut être utile pour les administrateurs 2015 de Skype entreprise Server qui aimeraient voir la topologie de réseau CAC pour leur déploiement sous forme graphique.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-540">This tool can be a valuable resource to Skype for Business Server 2015 administrators who would like to view CAC network topology for their deployment in a graphical format.</span></span>

## <a name="response-group-agent-live"></a><span data-ttu-id="7bcd9-541">Response Group Agent Live</span><span class="sxs-lookup"><span data-stu-id="7bcd9-541">Response Group Agent Live</span></span>
<span data-ttu-id="7bcd9-542"><a name="RGAL"> </a></span><span class="sxs-lookup"><span data-stu-id="7bcd9-542"></span></span>

<span data-ttu-id="7bcd9-543">L’application Response Group permet aux agents d’accéder à des informations utiles en temps réel via son service web intégré.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-543">The Response Group application gives agents the ability to access useful real-time information using its built-in Web service.</span></span> <span data-ttu-id="7bcd9-544">Aucun affichage graphique de ces données n’est toutefois disponible en dehors de l’application.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-544">Unfortunately, no graphical view of this data is available outside the application.</span></span> <span data-ttu-id="7bcd9-545">Pour résoudre ce problème, l’outil Response Group agent pour le kit de ressources techniques permet d’accéder à ces informations à l’aide d’un outil simple et graphique, tel que la présence d’autres agents.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-545">The Response Group Agent Live Resource Kit tool solves this issue by providing a simple and graphical way to access this information, enhanced with real-time Skype for Business communications software information such as the presence of other agents.</span></span>

### <a name="description"></a><span data-ttu-id="7bcd9-546">Description</span><span class="sxs-lookup"><span data-stu-id="7bcd9-546">Description</span></span>

<span data-ttu-id="7bcd9-547">L’application Windows Response Group Agent Live fournit des fonctionnalités de connexion et de déconnexion et donne des informations en temps réel (appartenance aux groupes, nombre actuel d’appels, etc.) aux agents Response Group.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-547">Response Group Agent Live is a Windows application that provides sign-in and sign-out functionality and some real-time information (such as group membership and current number of calls) to Response Group agents.</span></span> <span data-ttu-id="7bcd9-548">Il s’agit d’une version améliorée de la page groupes d’agents (accessible à partir de Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-548">It is meant to be an enhanced version of the Agent Groups page (accessible from Skype for Business.</span></span>

### <a name="purpose"></a><span data-ttu-id="7bcd9-549">Objectif</span><span class="sxs-lookup"><span data-stu-id="7bcd9-549">Purpose</span></span>

<span data-ttu-id="7bcd9-p161">L’application Response Group place les appels entrants en file d’attente avant de les acheminer vers des groupes d’agents. Pour identifier les appels à traiter de façon appropriée, les agents peuvent accéder à des informations en temps réel sur leurs groupes d’agents (agents disponibles, nombre d’appels en attente dans chaque file d’attente, etc.). Ces informations, à l’origine accessibles via le service Response Group uniquement, sont mises à disposition de façon intuitive par Response Group Agent Live.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-p161">The Response Group application queues incoming calls, and then routes them to agent groups. To make informed decisions about which calls to service, agents can access real-time information about their agent groups, such as what other agents are available and how many calls are waiting in each queue. This information, initially accessible only through the Response Group service, is made available in an intuitive way by Response Group Agent Live.</span></span>

#### <a name="features"></a><span data-ttu-id="7bcd9-553">Fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="7bcd9-553">Features</span></span>

<span data-ttu-id="7bcd9-554">L’outil Live Response agent agent est intégré au service Response Group et au kit de développement logiciel (SDK) Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-554">The Response Group Agent Live tool is built on the Response Group service and the Skype for Business Server 2015 SDK.</span></span> <span data-ttu-id="7bcd9-555">Il fournit aux agents Response Group les informations et fonctionnalités disponibles via le service Response Group (appartenance à des groupes, présence des autres agents, nombre d’appels en attente, etc.).</span><span class="sxs-lookup"><span data-stu-id="7bcd9-555">It provides Response Group agents the information and capabilities that are available from the Response Group service (such as group membership, presence of other agents, and number of waiting calls).</span></span>

<span data-ttu-id="7bcd9-556">La figure suivante illustre l’interface principale de Response Group Agent Live.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-556">The figure below illustrates the main interface of Response Group Agent Live.</span></span>

![Outil en ligne de l’agent Response Group.](../media/Reskit_2012_Tools_Documentation_Image37.JPG)

<span data-ttu-id="7bcd9-558">Les trois fonctionnalités principales suivantes sont accessibles aux agents dans Response Group Agent Live :</span><span class="sxs-lookup"><span data-stu-id="7bcd9-558">The following three main features are available for agents in Response Group Agent Live:</span></span>

- <span data-ttu-id="7bcd9-559">**Se connecter/** déconnecter : Contrairement à la page groupes d’agents (accessible depuis Skype entreprise Server 2015), l’agent Response Group n’autorise que les agents à se connecter ou se déconnecter de tous les groupes d’agents en même temps.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-559">**Sign-in/out:** Contrary to the Agent Groups page (accessible from Skype for Business Server 2015), Response Group Agent Live allows only agents to sign-in or out of all agent groups at once.</span></span> <span data-ttu-id="7bcd9-560">Cette application propose trois méthodes rapides pour la connexion ou la déconnexion des agents :</span><span class="sxs-lookup"><span data-stu-id="7bcd9-560">This application provides three quick ways for agents to sign in or out:</span></span>

  - <span data-ttu-id="7bcd9-561">Cliquer sur les boutons Sign-in/out (Connexion/Déconnexion) (vert et rouge) dans l’application.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-561">Click the Sign-in/out (green and red) buttons within the application.</span></span>

  - <span data-ttu-id="7bcd9-562">Cliquer avec le bouton droit sur la barre d’état système, et sélectionner Sign in (Connexion) ou Sign out (Déconnexion).</span><span class="sxs-lookup"><span data-stu-id="7bcd9-562">Right-click the system tray icon, and select sign in or sign out.</span></span>

  - <span data-ttu-id="7bcd9-563">Utiliser des raccourcis clavier configurables.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-563">Using configurable keyboard shortcuts.</span></span>

- <span data-ttu-id="7bcd9-564">**Appartenance à un groupe :** Lorsqu’un groupe d’agent est sélectionné, l’option agent de Response Group affiche la liste des agents de ce groupe dans le volet droit.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-564">**Group membership:** When an agent group is selected, Response Group Agent Live displays the list of agents in this group in the right pane.</span></span> <span data-ttu-id="7bcd9-565">Si Skype entreprise Server 2015 est en cours d’exécution sur le même ordinateur que cette application, les informations de présence et la carte de visite s’affichent dans l’agent Response Group Live.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-565">If Skype for Business Server 2015 is running on the same computer as this application, presence information and the contact card are displayed in the Response Group Agent Live.</span></span> <span data-ttu-id="7bcd9-566">Les agents peuvent envoyer un message instantané ou appeler d’autres agents directement depuis là.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-566">Agents can send an IM or call other agents directly from there.</span></span>

- <span data-ttu-id="7bcd9-p165">**Statistiques en temps réel :** Response Group Agent Live fournit des statistiques en temps réel pour tous les groupes d’agents. La fréquence de mise à jour est d’une minute. Lorsqu’un Response Group répond à un appel, un indicateur visuel est ajouté près du nom du groupe et le nombre actuel d’appels placés en file d’attente est indiqué. Pour afficher le délai d’attente le plus long, il suffit de placer le pointeur de la souris sur un groupe.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-p165">**Real-time statistics:** Response Group Agent Live provides real-time statistics for all agent groups. The update frequency is one minute. When a call is answered by a Response Group, a visual indicator is added next to the group name with the current number of queued calls. Pausing the pointer over a group also displays the longest waiting time.</span></span>

### <a name="requirements"></a><span data-ttu-id="7bcd9-571">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="7bcd9-571">Requirements</span></span>

<span data-ttu-id="7bcd9-572">Response Group Agent Live nécessite .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-572">Response Group Agent Live requires the .NET Framework 4.0.</span></span> <span data-ttu-id="7bcd9-573">Par ailleurs, pour tirer parti des fonctionnalités de présence et de carte de visite, Skype entreprise doit être installé en local (et être en cours d’exécution).</span><span class="sxs-lookup"><span data-stu-id="7bcd9-573">In addition, to take advantage of the presence and contact card features, Skype for Business must be installed locally (and be running).</span></span>

#### <a name="configuration"></a><span data-ttu-id="7bcd9-574">Configuration</span><span class="sxs-lookup"><span data-stu-id="7bcd9-574">Configuration</span></span>

<span data-ttu-id="7bcd9-p167">Response Group Agent Live peut être personnalisé selon les préférences individuelles via la boîte de dialogue Options de l’application. L’administrateur peut également définir l’adresse de l’hôte par défaut en modifiant directement la propriété defaultHostAddress du fichier RGAgentLive.exe.config.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-p167">Response Group Agent Live can be customized to individual preferences by using the Options dialog box in the application. In addition, the administrator can define the default host address by editing directly the defaultHostAddress property of the RGAgentLive.exe.config file.</span></span>

<span data-ttu-id="7bcd9-p168">La figure suivante illustre la boîte de dialogue Options qui permet aux agents de configurer l’adresse de l’hôte et les raccourcis clavier. Pour accéder à cette boîte de dialogue, il suffit de cliquer sur le bouton Options dans la partie supérieure droite de l’interface principale.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-p168">The figure below illustrates the Options dialog box that agents can use to configure the host address and shortcut keys. This dialog is accessed by clicking the Options button on the top right of the main interface.</span></span>

![Boîte de dialogue Options d’agent de Response Group.](../media/Reskit_2012_Tools_Documentation_Image38.JPG)

<span data-ttu-id="7bcd9-580">Les trois paramètres suivants peuvent être personnalisés dans la configuration de Response Group Agent Live :</span><span class="sxs-lookup"><span data-stu-id="7bcd9-580">The following three different settings can be customized in the Response Group Agent Live configuration:</span></span>

- <span data-ttu-id="7bcd9-581">Adresse hôte : il s’agit généralement du nom de domaine complet (FQDN) du pool Web de l’agent.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-581">Host address: This is typically the web pool FQDN belonging to the agent's home pool.</span></span> <span data-ttu-id="7bcd9-582">L’adresse exacte du service Response Group est dérivée automatiquement en arrière-plan à partir de ces informations (en ajoutant le chemin d’accès correct après l’hôte).</span><span class="sxs-lookup"><span data-stu-id="7bcd9-582">The exact Response Group service address is automatically derived in the background from this information (by appending the right path after the host).</span></span>

- <span data-ttu-id="7bcd9-583">Shortcuts (Raccourcis) : les raccourcis exacts pour la connexion/déconnexion peuvent être personnalisés.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-583">Shortcuts: The exact shortcuts to sign-in/out can be customized.</span></span> <span data-ttu-id="7bcd9-584">La seule limitation réside dans le fait que les deux raccourcis doivent contenir la clé « logo Windows » (en plus d’au moins une autre clé).</span><span class="sxs-lookup"><span data-stu-id="7bcd9-584">The only limitation is that both shortcuts must contain the "Windows Logo" key (in addition to at least another key).</span></span>

- <span data-ttu-id="7bcd9-585">Start with Windows (Démarrer avec Windows) : l’application peut être configurée pour démarrer automatiquement avec Windows.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-585">Start with Windows: The application can be configured to start automatically with Windows.</span></span>

### <a name="examples"></a><span data-ttu-id="7bcd9-586">Exemples</span><span class="sxs-lookup"><span data-stu-id="7bcd9-586">Examples</span></span>

<span data-ttu-id="7bcd9-587">La figure suivante illustre l’appel d’un autre agent ou l’envoi d’un message instantané à un autre agent en cliquant avec le bouton droit sur le contact dans le volet droit.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-587">The figure below illustrates how to call or send an IM to another agent by right-clicking the contact in the right pane.</span></span>

![Passer un appel ou envoyer un message instantané.](../media/Reskit_2012_Tools_Documentation_Image39.JPG)

<span data-ttu-id="7bcd9-589">La figure suivante illustre l’affichage par Response Group Agent Live du nombre actuel d’appels dans la file d’attente et le délai d’attente le plus long parmi tous les appels entrants.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-589">The figure below illustrates how Response Group Agent Live displays the current number of calls in the queue and the longest waiting time among all these incoming calls.</span></span>

![Affichage des informations de la file d’attente.](../media/Reskit_2012_Tools_Documentation_Image40.JPG)

### <a name="summary"></a><span data-ttu-id="7bcd9-591">Résumé</span><span class="sxs-lookup"><span data-stu-id="7bcd9-591">Summary</span></span>

<span data-ttu-id="7bcd9-592">Les connexion et déconnexion rapides, l’appartenance aux groupes et les statistiques de base en temps réel constituent des fonctionnalités intéressantes de Response Group Agent seulement disponibles en dehors de l’application à partir du service Response Group.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-592">Fast sign-in and sign-out, group membership, and basic real-time statistics are interesting Response Group agent features that are only available outside the application from the Response Group service.</span></span> <span data-ttu-id="7bcd9-593">À l’aide de l’outil Kit de ressources de l’agent Response Group, les administrateurs 2015 de Skype entreprise Server peuvent fournir à leurs agents une application Windows qui leur permet d’effectuer des tâches de manière plus rapide et graphique.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-593">With the Response Group Agent Live Resource Kit tool, Skype for Business Server 2015 administrators can provide their agents with a Windows application that allows them to perform tasks in a faster and graphical way.</span></span>

## <a name="sefautil"></a><span data-ttu-id="7bcd9-594">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="7bcd9-594">SEFAUtil</span></span>
<span data-ttu-id="7bcd9-595"><a name="SEFAUtil"> </a></span><span class="sxs-lookup"><span data-stu-id="7bcd9-595"></span></span>

<span data-ttu-id="7bcd9-596">SEFAUtil (Secondary Extension Feature activation) est un outil de ligne de commande qui permet aux administrateurs de logiciels de Skype entreprise 2015 Server et aux agents de support technique de configurer la sonnerie de délégué, le transfert d’appel et la sonnerie simultanée. pour le compte d’un utilisateur de Skype entreprise Server 2015 et les paramètres d’appel d’équipe.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-596">SEFAUtil (secondary extension feature activation) is a command-line tool that enables Skype for Business Server 2015 communications software administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Skype for Business Server 2015 user.</span></span> <span data-ttu-id="7bcd9-597">L’outil permet également aux administrateurs d’interroger les paramètres de routage des appels publiés pour un utilisateur particulier. L’outil SEFAUtil permet à l’administrateur d’activer/désactiver/modifier le transfert d’appel ou la sonnerie simultanée pour le compte de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-597">The tool also allows administrators to query the call-routing settings that are published for a particular user.The SEFAUtil tool allows the administrator to enable/disable/modify call forwarding or simultaneously ringing on behalf of the user.</span></span> <span data-ttu-id="7bcd9-598">L’administrateur peut spécifier la cible (sous la forme d’un URI SIP) ou utiliser une cible qui a déjà été publiée par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-598">The administrator can specify the target (in the form of a SIP URI) or use a target that has already been published by the user.</span></span> <span data-ttu-id="7bcd9-599">Cet outil permet également aux administrateurs d’ajouter ou de supprimer des délégués ou des membres du groupe d’appel d’équipe pour le compte de l’utilisateur. Cet outil est bâti sur le 3,0 de Microsoft Unified Communications Management API (UCMA) et nécessite que les administrateurs créent une application fiable dans le magasin central de gestion pour SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-599">This tool also allows administrators to add or remove delegates or team-call group members on behalf of the user.This tool is built on Microsoft Unified Communications Managed API (UCMA) 3.0 and requires that administrators create a trusted application in the Central Management store for SEFAUtil.</span></span>

<span data-ttu-id="7bcd9-600">SEFAUtil (activation de la fonctionnalité d’extension secondaire) permet aux administrateurs et aux agents d’assistance technique de Skype entreprise Server 2015 de configurer la sonnerie de délégué, le transfert d’appel, la sonnerie simultanée, les paramètres d’appel d’équipe et le prélèvement d’appel de groupe pour le compte d’un compte Skype. pour l’utilisateur de Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-600">SEFAUtil (secondary extension feature activation) enables Skype for Business Server 2015 administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Skype for Business Server 2015 user.</span></span> <span data-ttu-id="7bcd9-601">L’outil permet également aux administrateurs d’interroger les paramètres de routage des appels publiés pour un utilisateur particulier.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-601">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span>

### <a name="description"></a><span data-ttu-id="7bcd9-602">Description</span><span class="sxs-lookup"><span data-stu-id="7bcd9-602">Description</span></span>

<span data-ttu-id="7bcd9-603">La version actuelle de SEFAUtil n’est qu’un outil en ligne de commande, sans interface utilisateur graphique.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-603">The current version of SEFAUtil is only a command-line tool; there is no supporting graphical user interface.</span></span> <span data-ttu-id="7bcd9-604">Cet outil repose sur le 3,0 de Microsoft Unified Communications Managed API (UCMA).</span><span class="sxs-lookup"><span data-stu-id="7bcd9-604">This tool is based on Microsoft Unified Communications Managed API (UCMA) 3.0.</span></span> <span data-ttu-id="7bcd9-605">Ses fonctionnalités permettent aux administrateurs et agents du support technique d’effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="7bcd9-605">The features in this tool allow administrators and helpdesk agents to do the following:</span></span>

- <span data-ttu-id="7bcd9-606">afficher les paramètres de routage des appels d’un utilisateur (transfert d’appel, délégation, sonnerie simultanée, appel d’équipe et prise d’appel de groupe inclus) ;</span><span class="sxs-lookup"><span data-stu-id="7bcd9-606">View all call routing settings for a user (includes call-forwarding, delegation, simultaneous ringing, team-call and group call pickup)</span></span>

- <span data-ttu-id="7bcd9-607">activer/désactiver/modifier les paramètres de transfert d’appel (destination et minuteur d’absence de réponse inclus) ;</span><span class="sxs-lookup"><span data-stu-id="7bcd9-607">Enable/disable/modify call-forwarding setting (includes destination and no-answer timer)</span></span>

- <span data-ttu-id="7bcd9-608">activer/désactiver/modifier les configurations immédiates de transfert d’appel ;</span><span class="sxs-lookup"><span data-stu-id="7bcd9-608">Enable/disable/modify call-forwarding immediate configurations</span></span>

- <span data-ttu-id="7bcd9-609">activer/désactiver/modifier les paramètres de délégation ;</span><span class="sxs-lookup"><span data-stu-id="7bcd9-609">Enable/disable/modify delegation settings</span></span>

- <span data-ttu-id="7bcd9-610">activer/désactiver/modifier les paramètres d’appel d’équipe ;</span><span class="sxs-lookup"><span data-stu-id="7bcd9-610">Enable/disable/modify team-call group settings</span></span>

    > [!NOTE]
    > <span data-ttu-id="7bcd9-611">Nouveauté de Skype entreprise Server 2015 SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="7bcd9-611">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

- <span data-ttu-id="7bcd9-612">activer/désactiver/modifier les paramètres de sonnerie simultanée (destination incluse) ;</span><span class="sxs-lookup"><span data-stu-id="7bcd9-612">Enable/disable/modify simultaneous ringing settings (includes destination)</span></span>

    > [!NOTE]
    > <span data-ttu-id="7bcd9-613">Nouveauté de Skype entreprise Server 2015 SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="7bcd9-613">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

- <span data-ttu-id="7bcd9-614">activer/désactiver/modifier les paramètres de prise d’appel de groupe.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-614">Enable/disable/modify group call pickup settings</span></span>

    > [!CAUTION]
    > <span data-ttu-id="7bcd9-615">Nouveauté de Skype entreprise Server 2015 SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="7bcd9-615">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

<span data-ttu-id="7bcd9-616">Cet outil présente les limitations suivantes :</span><span class="sxs-lookup"><span data-stu-id="7bcd9-616">This tool has the following limitations:</span></span>

- <span data-ttu-id="7bcd9-617">Pris en charge uniquement pour les utilisateurs hébergés dans un pool Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="7bcd9-617">Supported only for users homed in a Skype for Business Server pool</span></span>

- <span data-ttu-id="7bcd9-618">modification en bloc des paramètres de routage des appels de plusieurs utilisateurs non prise en charge.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-618">Bulk-edit of call routing settings for several users is not supported</span></span>

### <a name="output"></a><span data-ttu-id="7bcd9-619">Sortie</span><span class="sxs-lookup"><span data-stu-id="7bcd9-619">Output</span></span>

<span data-ttu-id="7bcd9-p175">La version actuelle de cet outil génère une sortie dans la fenêtre d’invite de commandes uniquement. Pour plus d’informations, voir la section Exemples plus loin dans ce document.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-p175">The current version of this tool provides output only in the Command Prompt window. For details, see the Examples section later in this document.</span></span>

### <a name="purpose"></a><span data-ttu-id="7bcd9-622">Objectif</span><span class="sxs-lookup"><span data-stu-id="7bcd9-622">Purpose</span></span>

<span data-ttu-id="7bcd9-623">Voici certains des principaux scénarios d’utilisation de cet outil :</span><span class="sxs-lookup"><span data-stu-id="7bcd9-623">Following are some of the key scenarios where this tool may be used:</span></span>

- <span data-ttu-id="7bcd9-624">Bob est une direction qui a été déplacée vers la téléphonie de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-624">Bob is an executive and has been moved to Skype for Business Server telephony.</span></span> <span data-ttu-id="7bcd9-625">Il dispose d’une délégation sur son système PBX existant.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-625">He has delegation on his existing PBX system.</span></span> <span data-ttu-id="7bcd9-626">Dans le cadre de la migration vers Skype entreprise Server 2015, l’administrateur est en mesure de configurer le routage de Bob pour refléter sa configuration de délégation existante.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-626">As part of the move to Skype for Business Server 2015, the administrator is able to configure Bob's routing to reflect his pre-existing delegation configuration.</span></span>

- <span data-ttu-id="7bcd9-p177">En plein déplacement, Alice réalise qu’elle attend un appel important d’un de ses clients. Elle se trouve toutefois à l’hôtel et n’a accès à aucun ordinateur. Elle contacte le support technique pour leur demander de transférer vers son numéro de téléphone portable tous les appels reçus sur son numéro de téléphone professionnel. Les membres du personnel du support technique peuvent effectuer cette opération de configuration pour elle.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-p177">Alice is travelling and realizes that she is expecting an important call from one of her customers. However, she is in a hotel and has no access to a computer. She calls the helpdesk and requests that they forward to her mobile number all the calls made to her work number. The helpdesk personnel are able to do the configuration on her behalf.</span></span>

- <span data-ttu-id="7bcd9-631">Les appels de Jean vers son numéro de téléphone mobile sont portés à la messagerie vocale mobile dès qu’il est au bureau ; Toutefois, les éléments semblent fonctionner correctement dans la plupart des autres emplacements.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-631">Joe's calls to his work number are going to his mobile voicemail whenever he is at work; however, things appear to be working correctly in most other locations.</span></span> <span data-ttu-id="7bcd9-632">Le technicien du support technique est en mesure de consulter la configuration de routage de Jean et découvre qu’il dispose d’une sonnerie simultanée configurée sur son téléphone mobile.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-632">The helpdesk technician is able to view Joe's routing configuration and discovers that Joe has simultaneous ringing configured to his mobile phone.</span></span> <span data-ttu-id="7bcd9-633">Le technicien demande à Joe la couverture mobile au bureau et est en mesure de déterminer qu’il est à l’origine de l’appel de la messagerie vocale mobile de Jean lorsque sa couverture de réseau est médiocre.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-633">The technician asks Joe about the mobile coverage at his office and is able to determine that the simultaneous ringing rule is what is causing the calls to go to Joe's mobile voicemail when his network coverage is poor.</span></span>

- <span data-ttu-id="7bcd9-634">Michel est un nouvel employé de contoso et il rejoint une nouvelle équipe sur laquelle tous les membres sont configurés pour l’appel d’équipe, lorsque le niveau d’activation de Skype entreprise Server 2015 est activé, l’administrateur est en mesure de définir les paramètres du groupe d’appel d’équipe afin d’inclure tous les nouveaux membres de l’équipe. par ailleurs, l’administrateur ajoute Michel en tant que membre du groupe d’appel d’équipe pour chacun des membres de son équipe.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-634">Mike is a new employee at Contoso and he's joining a new team on which all members are configured for team-call, when being enabled for Skype for Business Server 2015, the administrator is able to set his team-call group settings to include all his new team members, additionally, the administrator adds Mike as a team-call group member for each of the members in his team.</span></span>

- <span data-ttu-id="7bcd9-635">Une pratique du service client dépendant du service Ressources humaines de Contoso consiste à offrir un service personnel à tous les appelants dès le premier appel.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-635">A customer service practice in the human resources department at Contoso is to provide personal service for all callers since the first call.</span></span> <span data-ttu-id="7bcd9-636">Tous les membres du service étant assis à proximité les uns des autres, la sonnerie de tous les téléphones en même temps en raison de l’activation de l’appel d’équipe est très perturbant pour le personnel.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-636">Given that all members of the department sit very close to each other, having all phones ringing at the same time with team-call is very disruptive for the team.</span></span> <span data-ttu-id="7bcd9-637">Pour fournir le meilleur service sans perturber les membres de l’équipe, l’administrateur 2015 de Skype entreprise Server tire parti de la fonctionnalité de cueillette des appels de groupe.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-637">To provide the best service without disrupting the team members, the Skype for Business Server 2015 administrator takes advantage of the Group Call Pickup capability.</span></span> <span data-ttu-id="7bcd9-638">Il ajoute tous les membres du service à un groupe de prise d’appel et communique le numéro de ce groupe au service.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-638">The administrator adds all department members to a pickup group and communicates to the department the pickup group number.</span></span> <span data-ttu-id="7bcd9-639">Pierre remarque que le téléphone de Samira sonne, alors que celle-ci s’est absentée, et prend donc l’appel à partir de son propre bureau.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-639">When Samantha is absent from her desk, Joe notices her phone ringing and he proceeds to answer the call from his desk.</span></span>

### <a name="requirements"></a><span data-ttu-id="7bcd9-640">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="7bcd9-640">Requirements</span></span>

<span data-ttu-id="7bcd9-p180">L’outil SEFAUtil peut seulement être exécuté sur un ordinateur faisant partie d’un pool d’applications approuvées. UCMA 3.0 doit être installé sur cet ordinateur. Pour exécuter l’outil, une application approuvée avec l’ID d’application SEFAUtil doit être créée sur ce pool.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-p180">The SEFAUtil tool can be run only on a computer that is a part of a Trusted Application Pool. UCMA 3.0 must be installed on that computer. To run the tool, a new Trusted Application with the SEFAUtil application ID must be created on that pool.</span></span>

### <a name="creating-a-new-trusted-application-for-the-sefautil-tool"></a><span data-ttu-id="7bcd9-644">Création d’une application approuvée pour l’outil SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="7bcd9-644">Creating a new Trusted Application for the SEFAUtil tool</span></span>

1. <span data-ttu-id="7bcd9-645">L’outil SEFAUtil ne peut être exécuté que sur un ordinateur qui fait partie d’un pool d’applications approuvées.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-645">The SEFAUTil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="7bcd9-646">Le cas échéant, l’ajout d’un pool en tant que nouveau pool d’applications approuvé peut être réalisé via Skype entreprise Server Management Shell avec l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="7bcd9-646">If needed, adding a pool as a new trusted application pool can be done via the Skype for Business Server Management Shell with the following cmdlet:</span></span>

   ```PowerShell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

    > [!NOTE]
    > <span data-ttu-id="7bcd9-647">UCMA 3.0 doit être installé sur les ordinateurs qui seront utilisés pour exécuter l’outil SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-647">UCMA 3.0 must be installed on any computer that will be used to run the SEFAUtil tool.</span></span>

2. <span data-ttu-id="7bcd9-648">Une application approuvée doit être définie dans la topologie pour l’outil SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-648">A trusted application needs to be defined in the topology for the SEFAUtil tool.</span></span> <span data-ttu-id="7bcd9-649">Pour définir SEFAUtil en tant que nouvelle application fiable, utilisez Skype entreprise Server Management Shell et exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="7bcd9-649">To define SEFAUtil as a new trusted application, use the Skype for Business Server Management Shell and execute the following cmdlet:</span></span>

   ```PowerShell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN> -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="7bcd9-650">Un autre port peut être utilisé au besoin.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-650">A different port can be used if needed.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7bcd9-651">Nom de domaine complet (FQDN) du pool : nom de domaine complet (FQDN) du serveur ou du pool hébergeant l’application SEFAUtil (généralement un serveur frontal Skype entreprise > ou un pool).</span><span class="sxs-lookup"><span data-stu-id="7bcd9-651">Pool FQDN: The FQDN of the server or pool that will host the SEFAUtil application (usually a Skype for Business Front End server     > or pool).</span></span>
    > <span data-ttu-id="7bcd9-652">Nom de domaine complet (FQDN) de pool : nom de domaine complet (FQDN) du serveur frontal ou du pool Skype entreprise associé à ce pool d’applications.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-652">Pool Registrar FQDN: The FQDN of the Skype for Business Front End server or pool associated with this application pool.</span></span>
    > <span data-ttu-id="7bcd9-653">Site du pool : ID de site du site sur lequel ce pool est hébergé.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-653">Pool Site: The Site ID of the site on which this pool is homed.</span></span>

3. <span data-ttu-id="7bcd9-654">Les modifications apportées à la topologie doivent être activées.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-654">The topology changes need to be enabled.</span></span> <span data-ttu-id="7bcd9-655">Il est possible d’activer les changements de topologie par le biais de Skype entreprise Server Management Shell en exécutant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="7bcd9-655">Enabling the topology changes can be done via the Skype for Business Server Management Shell by executing the following cmdlet:</span></span>

   ```PowerShell
   Enable-CsToplogy
   ```

4. <span data-ttu-id="7bcd9-656">Le cas échéant, installez les outils du kit de ressources Skype entreprise Server 2015 sur le serveur qui sera utilisé pour exécuter l’outil SEFAUtil (le serveur doit faire partie d’un pool d’applications approuvé).</span><span class="sxs-lookup"><span data-stu-id="7bcd9-656">If needed, install the Skype for Business Server 2015 Resource Kit Tools in the server that will be used to run the SEFAUtil tool (the server must be part of a trusted application pool).</span></span>

5. <span data-ttu-id="7bcd9-657">Vérifiez que SEFAUtil est correctement exécuté.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-657">Verify the SEFAUtil is running correctly.</span></span> <span data-ttu-id="7bcd9-658">Pour ce faire, exécutez l’outil à partir d’une invite de commandes de Windows avec des privilèges d’administrateur pour afficher les paramètres de transfert d’appel d’un utilisateur dans le déploiement.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-658">To do this, run the tool from a windows command prompt with administrator privileges to display the call forwarding settings of a user in the deployment.</span></span> <span data-ttu-id="7bcd9-659">Par défaut, l’outil se trouve à l’emplacement suivant : « . ..\Program Files\Skype pour Business Server 2015 \ reskit ».</span><span class="sxs-lookup"><span data-stu-id="7bcd9-659">By default the tool will be located in: "…\Program Files\Skype for Business Server 2015\Reskit".</span></span> <span data-ttu-id="7bcd9-660">Pour afficher les paramètres de transfert d’appel d’un utilisateur, utilisez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="7bcd9-660">To display the call forwarding settings of a user, use the following command:</span></span>

   ```console
   SEFAUtil.exe <user SIP address> /server:<Skype for Business Server/Pool FQDN>
   ```

    <span data-ttu-id="7bcd9-661">Les paramètres de transfert d’appel de l’utilisateur doivent s’afficher.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-661">The call forwarding settings of the user should be displayed.</span></span>

#### <a name="group-call-pickup"></a><span data-ttu-id="7bcd9-662">Prise d’appel de groupe</span><span class="sxs-lookup"><span data-stu-id="7bcd9-662">Group Call Pickup</span></span>

<span data-ttu-id="7bcd9-663">La fonction de cueillette des appels de groupe nécessite une configuration supplémentaire dans Skype entreprise Server 2015 pour pouvoir être entièrement activée.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-663">Group Call Pickup requires additional configuration in Skype for Business Server 2015 for the capability to be fully enabled.</span></span> <span data-ttu-id="7bcd9-664">Avant d’affecter les groupes de prise d’appels aux utilisateurs, consultez la documentation sur la prise d’appel de groupe pour connaître les étapes de planification et de déploiement de cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-664">Before assigning pickup groups to users, refer to the Group Call Pickup product documentation for the planning and deployment steps of this capability.</span></span>

### <a name="examples"></a><span data-ttu-id="7bcd9-665">Exemples</span><span class="sxs-lookup"><span data-stu-id="7bcd9-665">Examples</span></span>

#### <a name="display-current-call-handling-settings"></a><span data-ttu-id="7bcd9-666">Afficher les paramètres actuels de gestion des appels</span><span class="sxs-lookup"><span data-stu-id="7bcd9-666">Display Current Call Handling Settings</span></span>

<span data-ttu-id="7bcd9-667">La commande suivante affiche le traitement des appels pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-667">The following command displays the call handling for the user.</span></span>  `SEFAUtil.exe /server:SfBS2015server.contoso.com katarina@contoso.com`

> [!NOTE]
> <span data-ttu-id="7bcd9-668">Cet exemple utilise le commutateur **/Server** pour spécifier la connexion de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-668">This example uses the **/server** switch to specify the Skype for Business Server to connect to.</span></span>

 <span data-ttu-id="7bcd9-669">**Sortie**</span><span class="sxs-lookup"><span data-stu-id="7bcd9-669">**Output**</span></span>

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:20
Call Forward No Answer to: voicemail
```

#### <a name="set-the-call-forwardno-answer-destination"></a><span data-ttu-id="7bcd9-670">Définir la destination du transfert d’appel/en cas d’absence de réponse</span><span class="sxs-lookup"><span data-stu-id="7bcd9-670">Set the Call Forward/No Answer Destination</span></span>

<span data-ttu-id="7bcd9-671">Cet exemple définit la destination d’appel/non de réponse et le délai de sonnerie.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-671">This example sets the call forward/no answer destination and the ring delay.</span></span> <span data-ttu-id="7bcd9-672">Ici, le commutateur/Server n’est pas fourni ; SEFAUtil tente d’établir une découverte automatique de Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-672">Here, the /server switch is not provided; SEFAUtil attempts to autodiscover the Skype for Business Server 2015.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone
```

 <span data-ttu-id="7bcd9-673">**Sortie**</span><span class="sxs-lookup"><span data-stu-id="7bcd9-673">**Output**</span></span>

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="enable-call-forwarding-immediately"></a><span data-ttu-id="7bcd9-674">Activer le transfert d’appel immédiatement</span><span class="sxs-lookup"><span data-stu-id="7bcd9-674">Enable Call Forwarding Immediately</span></span>

<span data-ttu-id="7bcd9-675">Cet exemple active immédiatement le transfert d’appel vers un autre utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-675">This example immediately enables call-forwarding to another user.</span></span>

```
SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com
```

 <span data-ttu-id="7bcd9-676">**Sortie**</span><span class="sxs-lookup"><span data-stu-id="7bcd9-676">**Output**</span></span>

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Forward immediate to: sip:anders@contoso.com
```

#### <a name="disable-call-forwarding-immediately"></a><span data-ttu-id="7bcd9-677">Désactiver immédiatement le transfert d’appel</span><span class="sxs-lookup"><span data-stu-id="7bcd9-677">Disable Call Forwarding Immediately</span></span>

<span data-ttu-id="7bcd9-678">Cet exemple désactivé immédiatement le transfert d’appel.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-678">This example immediately disables call forwarding.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com katarina@contoso.com  /disablefwdimmediate
```

 <span data-ttu-id="7bcd9-679">**Sortie**</span><span class="sxs-lookup"><span data-stu-id="7bcd9-679">**Output**</span></span>

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a><span data-ttu-id="7bcd9-680">Ajouter un utilisateur en tant que délégué et définir la sonnerie simultanée des délégués</span><span class="sxs-lookup"><span data-stu-id="7bcd9-680">Add a User as a Delegate and Set Up Simultaneous Ringing of Delegates</span></span>

<span data-ttu-id="7bcd9-681">Cet exemple ajoute un utilisateur en tant que délégué et définit la sonnerie simultanée des délégués.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-681">This example adds a user as a delegate and sets up simultaneous ringing of delegates.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates
```

 <span data-ttu-id="7bcd9-682">**Sortie**</span><span class="sxs-lookup"><span data-stu-id="7bcd9-682">**Output**</span></span>

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simultaneously Ringing Delegates: sip:joe@contoso.com
```

#### <a name="change-simultaneous-ringing-rule-of-delegates"></a><span data-ttu-id="7bcd9-683">Modifier la règle de sonnerie simultanée des délégués</span><span class="sxs-lookup"><span data-stu-id="7bcd9-683">Change Simultaneous Ringing Rule of Delegates</span></span>

<span data-ttu-id="7bcd9-684">Cet exemple modifie la règle de sonnerie simultanée définie dans l’exemple précédent en règle de sonnerie différée.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-684">This example changes the simultaneous ringing rule that was set in the previous example to the delayed ringing rule.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10
```

 <span data-ttu-id="7bcd9-685">**Sortie**</span><span class="sxs-lookup"><span data-stu-id="7bcd9-685">**Output**</span></span>

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com
```

#### <a name="remove-the-delegate"></a><span data-ttu-id="7bcd9-686">Supprimer le délégué</span><span class="sxs-lookup"><span data-stu-id="7bcd9-686">Remove the Delegate</span></span>

<span data-ttu-id="7bcd9-687">Cet exemple supprime le délégué.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-687">This example removes the delegate.</span></span>

> [!NOTE]
> <span data-ttu-id="7bcd9-688">Une fois le dernier délégué supprimé, la sonnerie sur le poste de délégués est désactivée automatiquement.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-688">When the last delegate is removed, delegate ringing is automatically disabled.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com
```

 <span data-ttu-id="7bcd9-689">**Sortie**</span><span class="sxs-lookup"><span data-stu-id="7bcd9-689">**Output**</span></span>

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a><span data-ttu-id="7bcd9-690">Ajouter un délégué et définir la règle de transfert d’appel aux délégués</span><span class="sxs-lookup"><span data-stu-id="7bcd9-690">Add a Delegate and Set Up the Call-Forward to Delegates Rule</span></span>

<span data-ttu-id="7bcd9-691">Cet exemple ajoute un délégué et définit la règle de transfert d’appel aux délégués.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-691">This example adds a delegate and sets up the call-forward to delegates rule.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates
```

 <span data-ttu-id="7bcd9-692">**Sortie**</span><span class="sxs-lookup"><span data-stu-id="7bcd9-692">**Output**</span></span>

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Forwarding calls to Delegates: sip:anders@contoso.com
```

#### <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a><span data-ttu-id="7bcd9-693">Activer la sonnerie simultanée et définir un numéro de destination</span><span class="sxs-lookup"><span data-stu-id="7bcd9-693">Enable Simultaneous Ringing and Set a Destination Number</span></span>

<span data-ttu-id="7bcd9-694">Cet exemple active la sonnerie simultanée et définit un numéro de destination pour la sonnerie simultanée.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-694">This example enables simultaneous ringing and sets a simultaneous ringing destination number.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring
```

> [!NOTE]
> <span data-ttu-id="7bcd9-695">Pour modifier le numéro de destination de la sonnerie simultanée d’un utilisateur pour lequel la sonnerie simultanée est déjà activée, conservez la commande avec le commutateur /enablesimulring, sans quoi le numéro de destination ne sera pas modifié.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-695">To change the simultaneous ringing destination number of a user that has already simultaneous ringing enabled, keep the command with the /enablesimulring switch, otherwise the destination number will not be changed.</span></span>

 <span data-ttu-id="7bcd9-696">**Sortie**</span><span class="sxs-lookup"><span data-stu-id="7bcd9-696">**Output**</span></span>

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: True
Simul_Ringing to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="disable-simultaneous-ringing"></a><span data-ttu-id="7bcd9-697">Désactiver la sonnerie simultanée</span><span class="sxs-lookup"><span data-stu-id="7bcd9-697">Disable Simultaneous Ringing</span></span>

<span data-ttu-id="7bcd9-698">Cet exemple désactive la sonnerie simultanée.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-698">This example disables simultaneous ringing.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablesimulring
```

 <span data-ttu-id="7bcd9-699">**Sortie**</span><span class="sxs-lookup"><span data-stu-id="7bcd9-699">**Output**</span></span>

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a><span data-ttu-id="7bcd9-700">Ajouter un membre d’équipe pour l’appel d’équipe et définir la sonnerie simultanée sur le groupe d’appel d’équipe</span><span class="sxs-lookup"><span data-stu-id="7bcd9-700">Add a Team Member for Team-Call and Set up Simultaneous Ringing to the Team-Call Members Group</span></span>

<span data-ttu-id="7bcd9-701">Cet exemple ajoute un membre d’équipe au groupe d’appel d’équipe d’un utilisateur et active la sonnerie simultanée sur le groupe d’appel d’équipe.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-701">This example adds a team member to the team-call group of a user and enables simultaneous ringing to the team-call group.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam
```

> [!NOTE]
> <span data-ttu-id="7bcd9-702">L’ajout d’un membre au groupe d’appel d’équipe d’un utilisateur définit automatiquement les paramètres de sonnerie simultanée des utilisateurs sur la sonnerie simultanée de son groupe d’appel d’équipe.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-702">Adding a member to the team-call group of a user will automatically switch the simultaneous ringing settigs of the users to simulring his team-call group.</span></span>

 <span data-ttu-id="7bcd9-703">**Sortie**</span><span class="sxs-lookup"><span data-stu-id="7bcd9-703">**Output**</span></span>

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Team ringing enabled. Team: sip:anders@contoso.com
```

#### <a name="remove-a-member-from-the-team-call-group"></a><span data-ttu-id="7bcd9-704">Supprimer un membre du groupe d’appel d’équipe</span><span class="sxs-lookup"><span data-stu-id="7bcd9-704">Remove a Member from the Team-Call Group</span></span>

<span data-ttu-id="7bcd9-705">Cet exemple supprime un membre d’équipe du groupe d’appel d’équipe d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-705">This example removes a team member of the team-call group of a user.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com
```

> [!NOTE]
> <span data-ttu-id="7bcd9-706">Si le membre supprimé est le seul du groupe d’appel d’équipe, la sonnerie simultanée du groupe d’appel d’équipe est automatiquement désactivée.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-706">If the member being removed is the only member of the team-call group, simultaneously ringing to the team-call group will be automatically disabled.</span></span>

 <span data-ttu-id="7bcd9-707">**Sortie**</span><span class="sxs-lookup"><span data-stu-id="7bcd9-707">**Output**</span></span>

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="set-the-delayed-ring-to-the-team-call-group"></a><span data-ttu-id="7bcd9-708">Définir la sonnerie différée sur le groupe d’appel d’équipe</span><span class="sxs-lookup"><span data-stu-id="7bcd9-708">Set the Delayed Ring to the Team-Call Group</span></span>

<span data-ttu-id="7bcd9-709">Cet exemple définit la sonnerie différée sur le paramètre d’heure du groupe d’appel d’équipe.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-709">This example changes the delayed ring to the team-call group time setting.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringteam:5
```

 <span data-ttu-id="7bcd9-710">**Sortie**</span><span class="sxs-lookup"><span data-stu-id="7bcd9-710">**Output**</span></span>

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com
```

#### <a name="enable-team-call"></a><span data-ttu-id="7bcd9-711">Activer l’appel d’équipe</span><span class="sxs-lookup"><span data-stu-id="7bcd9-711">Enable Team-Call</span></span>

<span data-ttu-id="7bcd9-712">Cet exemple active l’appel d’équipe pour un utilisateur donné.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-712">This example enables team-call for a given user.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /simulringteam
```

> [!NOTE]
> <span data-ttu-id="7bcd9-713">Si le groupe d’appel d’équipe de l’utilisateur ne possède pas de membre, l’appel d’équipe n’est pas activé.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-713">If the team-call group of the user has no members, team-call won't be enabled.</span></span>

 <span data-ttu-id="7bcd9-714">**Sortie**</span><span class="sxs-lookup"><span data-stu-id="7bcd9-714">**Output**</span></span>

#### <a name="disable-team-call"></a><span data-ttu-id="7bcd9-715">Désactiver l’appel d’équipe</span><span class="sxs-lookup"><span data-stu-id="7bcd9-715">Disable Team-Call</span></span>

<span data-ttu-id="7bcd9-716">Cet exemple désactive l’appel d’équipe pour un utilisateur donné.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-716">This example disables team-call for a given user.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disableteamcall
```

 <span data-ttu-id="7bcd9-717">**Sortie**</span><span class="sxs-lookup"><span data-stu-id="7bcd9-717">**Output**</span></span>

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a><span data-ttu-id="7bcd9-718">Activer la prise d’appel de groupe et affecter un groupe de prise d’appel à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="7bcd9-718">Enable Group Call Pickup and Assign a Pickup Group to a User</span></span>

<span data-ttu-id="7bcd9-719">Cet exemple affecte un groupe de prise d’appel à un utilisateur et active la prise d’appel de groupe.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-719">This example assigns a pickup group to a user and enables Group Call Pickup.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199
```

 <span data-ttu-id="7bcd9-720">**Sortie**</span><span class="sxs-lookup"><span data-stu-id="7bcd9-720">**Output**</span></span>

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone
```

#### <a name="disable-group-call-pickup"></a><span data-ttu-id="7bcd9-721">Désactiver la prise d’appel de groupe</span><span class="sxs-lookup"><span data-stu-id="7bcd9-721">Disable Group Call Pickup</span></span>

<span data-ttu-id="7bcd9-722">Cet exemple désactive la prise d’appel de groupe pour un utilisateur donné.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-722">This example disables Group Call Pickup for a given user.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablegrouppickup
```

> [!NOTE]
> <span data-ttu-id="7bcd9-p188">Lorsque vous désactivez la prise d’appel de groupe pour un utilisateur, le numéro de groupe affecté à cet utilisateur n’est pas conservé. Si vous souhaitez ultérieurement réactiver la prise d’appel de groupe pour cet utilisateur, vous devez réaffecter le numéro de groupe avec le commutateur /enablegrouppickup.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-p188">When you disable Group Call Pickup for a user, the group number that was assigned to the user is not retained. If you subsequently want to re-enable Group Call Pickup for that user, you must assign the group number again with the /enablegrouppickup switch.</span></span>

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
```

## <a name="sysprepps1"></a><span data-ttu-id="7bcd9-725">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="7bcd9-725">SYSPrep.ps1</span></span>
<span data-ttu-id="7bcd9-726"><a name="SYSPrep"> </a></span><span class="sxs-lookup"><span data-stu-id="7bcd9-726"></span></span>

### <a name="description"></a><span data-ttu-id="7bcd9-727">Description</span><span class="sxs-lookup"><span data-stu-id="7bcd9-727">Description</span></span>

<span data-ttu-id="7bcd9-728">SYSPrep. ps1 est un script Windows PowerShell qui installe les conditions préalables de Skype entreprise Server 2015 requises sur votre ordinateur de système d’exploitation Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-728">SYSPrep.ps1 is a Windows PowerShell script that will install the following Skype for Business Server 2015 prerequisites on your Windows Server 2008 operating system machine.</span></span>

- <span data-ttu-id="7bcd9-729">Microsoft .Net Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="7bcd9-729">Microsoft .Net Framework 4.5</span></span>

- <span data-ttu-id="7bcd9-730">Microsoft SQL Server Express ;</span><span class="sxs-lookup"><span data-stu-id="7bcd9-730">Microsoft SQL Server Express</span></span>

- <span data-ttu-id="7bcd9-731">Windows Powershell version 3.0</span><span class="sxs-lookup"><span data-stu-id="7bcd9-731">Windows Powershell version 3.0</span></span>

- <span data-ttu-id="7bcd9-732">Visual C++ 2010 Redistributable</span><span class="sxs-lookup"><span data-stu-id="7bcd9-732">Visual C++ 2010 Redistributable</span></span>

- <span data-ttu-id="7bcd9-733">Mises à jour d’Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="7bcd9-733">Internet Information Server Updates</span></span>

- <span data-ttu-id="7bcd9-734">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="7bcd9-734">Windows Identity Foundation</span></span>

- <span data-ttu-id="7bcd9-735">Fichiers principaux de Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="7bcd9-735">Skype for Business Server 2015 Core files</span></span>

  <span data-ttu-id="7bcd9-736">Si le nom du script est semblable à l’outil de préparation du système pour les systèmes d’exploitation Microsoft Windows, ils sont toutefois différents.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-736">While the script name is similar to the System Preparation Tool for the Microsoft Windows operating systems, they are different.</span></span> <span data-ttu-id="7bcd9-737">Ce script installe uniquement les prérequis requis pour Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-737">This script will only install the required prerequisites for Skype for Business Server 2015.</span></span> <span data-ttu-id="7bcd9-738">Une fois ceux-ci installés, l’outil Windows SYSPrep peut ensuite être utilisé pour créer une image du serveur.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-738">Once those prerequisites are installed, the Windows SYSPrep tool can then be used to create an image of the server.</span></span>

### <a name="requirements"></a><span data-ttu-id="7bcd9-739">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="7bcd9-739">Requirements</span></span>

<span data-ttu-id="7bcd9-740">Avant d’exécuter le script SYSPrep. ps1, vous devez copier les fichiers requis vers un dossier local de l’ordinateur du système d’exploitation Windows Server 2008 (par exemple **, D:\setup)**.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-740">Prior to running the SYSPrep.ps1 script, you must copy the prerequisite files to a local folder on the Windows Server 2008 operating system machine (for example **D:\Setup)**.</span></span> <span data-ttu-id="7bcd9-741">Ce dossier doit également inclure une copie des fichiers 2015 de Skype entreprise Server, en particulier **Setup. exe.**</span><span class="sxs-lookup"><span data-stu-id="7bcd9-741">This folder must also include a copy of the Skype for Business Server 2015 files, specifically **Setup.exe.**</span></span> <span data-ttu-id="7bcd9-742">Les fichiers des logiciels prérequis peuvent être téléchargés aux emplacements suivants :</span><span class="sxs-lookup"><span data-stu-id="7bcd9-742">The prerequisite files can be downloaded from the following locations:</span></span>


| <span data-ttu-id="7bcd9-743">**Logiciels prérequis**</span><span class="sxs-lookup"><span data-stu-id="7bcd9-743">**Prerequisite**</span></span>                                | <span data-ttu-id="7bcd9-744">**Emplacement**</span><span class="sxs-lookup"><span data-stu-id="7bcd9-744">**Location**</span></span>                                                            |
|:------------------------------------------------|:------------------------------------------------------------------------|
| <span data-ttu-id="7bcd9-745">Microsoft .Net Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="7bcd9-745">Microsoft .Net Framework 4.5</span></span>  <br/>             | <https://go.microsoft.com/?linkid=9816306>  <br/>                       |
| <span data-ttu-id="7bcd9-746">Microsoft SQL Server Express 2008 R2</span><span class="sxs-lookup"><span data-stu-id="7bcd9-746">Microsoft SQL Server Express 2008 R2</span></span>  <br/>     | <https://www.microsoft.com/en-us/download/details.aspx?id=23650>  <br/> |
| <span data-ttu-id="7bcd9-747">Windows Powershell version 3.0</span><span class="sxs-lookup"><span data-stu-id="7bcd9-747">Windows Powershell version 3.0</span></span>  <br/>           | <https://www.microsoft.com/en-us/download/details.aspx?id=34595>  <br/> |
| <span data-ttu-id="7bcd9-748">Visual C++ 2010 Redistributable</span><span class="sxs-lookup"><span data-stu-id="7bcd9-748">Visual C++ 2010 Redistributable</span></span>  <br/>          | <https://www.microsoft.com/en-us/download/details.aspx?id=5555>  <br/>  |
| <span data-ttu-id="7bcd9-749">Mises à jour d’Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="7bcd9-749">Internet Information Server Updates</span></span>  <br/>      | <https://www.microsoft.com/en-us/download/details.aspx?id=34869>  <br/> |
| <span data-ttu-id="7bcd9-750">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="7bcd9-750">Windows Identity Foundation</span></span>  <br/>              | <https://www.microsoft.com/en-us/download/details.aspx?id=17331>  <br/> |
| <span data-ttu-id="7bcd9-751">Skype entreprise Server 2015 Setup. exe</span><span class="sxs-lookup"><span data-stu-id="7bcd9-751">Skype for Business Server 2015 Setup.exe</span></span>  <br/> | <span data-ttu-id="7bcd9-752">Copier à partir de Skype entreprise Server 2015 Media</span><span class="sxs-lookup"><span data-stu-id="7bcd9-752">Copy from Skype for Business Server 2015 media</span></span>  <br/>                   |

### <a name="parameter"></a><span data-ttu-id="7bcd9-753">Paramètre</span><span class="sxs-lookup"><span data-stu-id="7bcd9-753">Parameter</span></span>

<span data-ttu-id="7bcd9-754">Le paramètre **-SetupFolder** accepte en tant qu’argument l’emplacement du répertoire des fichiers prérequis</span><span class="sxs-lookup"><span data-stu-id="7bcd9-754">The **-SetupFolder** parameter takes as an argument the directory location of the prerequisite files</span></span>

### <a name="examples"></a><span data-ttu-id="7bcd9-755">Exemples</span><span class="sxs-lookup"><span data-stu-id="7bcd9-755">Examples</span></span>

<span data-ttu-id="7bcd9-756">Pour exécuter le script SYSPrep. ps1 et installer les prérequis Skype entreprise Server 2015, exécutez la commande suivante à partir d’une invite de commandes avec élévation de privilèges :</span><span class="sxs-lookup"><span data-stu-id="7bcd9-756">To run the SYSPrep.ps1 script and install the Skype for Business Server 2015 prerequisites, run the following command from an elevated command prompt:</span></span>

```console
./SysPrep.PS1 -SetupFolder D:\Setup
```

## <a name="unassigned-number-announcements-migration"></a><span data-ttu-id="7bcd9-757">Unassigned Number Announcements Migration</span><span class="sxs-lookup"><span data-stu-id="7bcd9-757">Unassigned Number Announcements Migration</span></span>
<span data-ttu-id="7bcd9-758"><a name="UNAM"> </a></span><span class="sxs-lookup"><span data-stu-id="7bcd9-758"></span></span>

<span data-ttu-id="7bcd9-759">L’outil de migration rendez-vous non attribué le numéro à l’aide d’un outil de migration Skype entreprise Server 2015 pour déplacer la configuration des numéros non attribués, qui est mise en service par l’application d’annonce à partir d’une source Skype entreprise Server ou d’un pool vers un destination Skype entreprise Server ou pool.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-759">The Unassigned Number Announcements Migration tool enables a Skype for Business Server 2015 administrator to move the unassigned numbers configuration that is serviced by the announcement application from a source Skype for Business Server or Pool to a destination Skype for Business Server or Pool.</span></span>

### <a name="description"></a><span data-ttu-id="7bcd9-760">Description</span><span class="sxs-lookup"><span data-stu-id="7bcd9-760">Description</span></span>

<span data-ttu-id="7bcd9-761">L’outil Unassigned Number Announcements Migration est un script Windows PowerShell qui déplace la configuration des numéros non attribués pris en charge par l’application d’annonce entre un pool ou un serveur source et un autre pool ou serveur.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-761">The Unassigned Number Announcements Migration tool is a Windows PowerShell script that moves the unassigned numbers configuration serviced by the announcement application of a source server or pool to a different server or pool.</span></span>

<span data-ttu-id="7bcd9-762">Lorsqu’il est exécuté, le script Unassigned Number Announcements Migration effectue les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="7bcd9-762">When executed, the Unassigned Number Announcements Migration script will perform the following operations:</span></span>

1. <span data-ttu-id="7bcd9-763">Déplacer tous les fichiers audio utilisés par les annonces de numéros non attribués de l’application d’annonce hébergée sur le pool ou serveur source vers le magasin de fichiers du pool ou serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-763">Move all the audio files used by the unassigned number announcements of the announcement application hosted in the source server or pool to the file store of the destination server or pool.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7bcd9-764">Les fichiers audio sont supprimés du pool de sources une fois qu’ils sont copiés sur le pool de destination.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-764">The audio files are removed from the source pool once they're copied to the destination pool.</span></span>

2. <span data-ttu-id="7bcd9-765">Déplacer les annonces de numéros non attribués configurées pour l’application d’annonce hébergée dans le pool ou serveur source vers le pool ou serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-765">Move all unassigned number announcements configured for the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

3. <span data-ttu-id="7bcd9-766">Réaffecter toutes les plages de numéros non attribués prises en charge par l’application d’annonce hébergée dans le pool ou serveur source vers le pool ou serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-766">Reassign all the unassigned number ranges that are serviced by the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

<span data-ttu-id="7bcd9-767">Une fois le script correctement exécuté, toutes les plages de numéros affectés prises en charge par l’application d’annonce hébergée dans le pool ou serveur source sont à présent prises en charge avec la même configuration par le pool ou le serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-767">After successfully running the script, all the unassigned number ranges that were serviced by the announcement application hosted in the source server or pool will now be serviced with the same configuration by the destination server or pool.</span></span>

### <a name="output"></a><span data-ttu-id="7bcd9-768">Sortie</span><span class="sxs-lookup"><span data-stu-id="7bcd9-768">Output</span></span>

<span data-ttu-id="7bcd9-769">Le script **Move-CsAnnouncementConfiguration** indique dans la fenêtre Skype entreprise Server Management Shell à partir de laquelle il a exécuté la réussite ou l’échec de l’opération de migration.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-769">The **Move-CsAnnouncementConfiguration** script indicates in the Skype for Business Server Management Shell window from where it's executed the success or failure of the migration operation.</span></span>

<span data-ttu-id="7bcd9-p191">Si l’exécution de l’opération est interrompue par une erreur, les plages de numéros non attribués correctement déplacées vers la destination sont conservées dans la destination sous une forme opérationnelle et le reste des plages de numéros non attribués à migrer sont conservés dans la source sous une forme opérationnelle également. Pour migrer entièrement le reste de la configuration, exécutez à nouveau le script après avoir traité l’erreur.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-p191">If the execution of the operation is interrupted by any error, the unassigned number ranges that were successfully moved to the destination will remain in the destination in an operational form and the rest of the unassigned number ranges to be migrated will remain in the source as well in an operational form. To fully migrate the rest of the configuration, rerun the script after addressing the error.</span></span>

### <a name="purpose"></a><span data-ttu-id="7bcd9-772">Objectif</span><span class="sxs-lookup"><span data-stu-id="7bcd9-772">Purpose</span></span>

<span data-ttu-id="7bcd9-773">Le script Unassigned Number Announcements Migration peut être utilisé dans le cadre des scénarios suivants :</span><span class="sxs-lookup"><span data-stu-id="7bcd9-773">The Unassigned Number Announcements Migration script can be used in the following three scenarios:</span></span>

- <span data-ttu-id="7bcd9-774">**Migration des paramètres de configuration vers une nouvelle version de Skype entreprise Server :** Contoso est en train de migrer vers Skype entreprise Server 2015 et dans le cadre du processus de migration, l’administrateur de votre serveur Skype entreprise souhaite déplacer la configuration des numéros non attribués, servie par l’application d’annonce, du déploiement de Lync Server 2013 vers le nouveau déploiement de Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-774">**Migrating configuration settings to a new version of Skype for Business Server:** Contoso is in the process of migrating to Skype for Business Server 2015 and as part of the migration process the Skype for Business Server administrator would like to move the unassigned numbers configuration serviced by the announcement application from the Lync Server 2013 deployment to the new Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="7bcd9-775">Pour modifier les paramètres de configuration, l’administrateur de Skype entreprise Server utilise l’outil de migration annonces de numéros non attribués.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-775">To move the configuration settings, the Skype for Business Server administrator uses the Unassigned Number Announcements Migration tool.</span></span>

- <span data-ttu-id="7bcd9-776">**Restauration d’un déploiement de Skype entreprise Server 2015 vers Lync server 2013 :** En raison de facteurs inattendus, contoso doit annuler la migration vers le nouveau déploiement de Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-776">**Rolling back a deployment from Skype for Business Server 2015 to Lync Server 2013:** Due unexpected factors, Contoso has to roll back the migration to the new Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="7bcd9-777">Pour limiter les perturbations du service, l’administrateur de votre serveur Skype entreprise utilise l’outil de migration annonces de numéros non attribués pour rétablir la configuration du déploiement de Skype entreprise Server 2015 sur le déploiement de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-777">To minimize disruptions to the service, the Skype for Business Server administrator uses the Unassigned Number Announcements Migration tool to roll back the configuration from the Skype for Business Server 2015 deployment to the Lync Server 2013 deployment.</span></span>

- <span data-ttu-id="7bcd9-778">**Déplacer des données entre des déploiements :** Contoso est en train de remplacer tous les serveurs d’un pool par des serveurs plus récents.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-778">**Moving data between deployments:** Contoso is in the process of replacing all the servers of one pool with newer servers.</span></span> <span data-ttu-id="7bcd9-779">Sa stratégie consiste à déployer un nouveau pool Skype entreprise Server 2015, à déplacer toutes les données de l’ancien vers le nouveau pool, puis à déconseiller l’ancien pool.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-779">Their strategy is to deploy a new Skype for Business Server 2015 pool, move all the data from the old to the new pool, and then deprecate the old pool.</span></span> <span data-ttu-id="7bcd9-780">Une fois le nouveau pool déployé, l’outil Unassigned Number Announcements Migration est utilisé pour déplacer la configuration de l’ancien pool vers le nouveau.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-780">Once the new pool is deployed, the Unassigned Number Announcements Migration tool is used to move the configuration from the old pool to the new one.</span></span>

#### <a name="requirements"></a><span data-ttu-id="7bcd9-781">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="7bcd9-781">Requirements</span></span>

<span data-ttu-id="7bcd9-782">Les principaux éléments de configuration suivants sont requis pour exécuter correctement l’outil :</span><span class="sxs-lookup"><span data-stu-id="7bcd9-782">The following are the main requirements needed to successfully run the tool:</span></span>

1. <span data-ttu-id="7bcd9-783">Le script doit être exécuté à partir d’un ordinateur sur lequel est installé Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-783">The script must be run from a computer that has Skype for Business Server Management Shell installed.</span></span>

2. <span data-ttu-id="7bcd9-784">Le déploiement de l’application d’annonce doit être effectué dans les serveurs ou pools Skype entreprise sources et cibles.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-784">The announcement application has to be successfully deployed in the source and destination Skype for Business Servers or Pools.</span></span>

#### <a name="move-csannouncementconfiguration-script"></a><span data-ttu-id="7bcd9-785">Script Move-CsAnnouncementConfiguration.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-785">Move-CsAnnouncementConfiguration script</span></span>

<span data-ttu-id="7bcd9-786">Le script Move-CsAnnouncementConfiguration nécessite les deux paramètres décrits dans le tableau suivant. </span><span class="sxs-lookup"><span data-stu-id="7bcd9-786">The Move-CsAnnouncementConfiguration script requires the two parameters that are described in the table below.</span></span>

![Paramètres de déplacement-CsAnnouncementConfiguration.](../media/Reskit_2012_Tools_Documentation_Image41.JPG)

### <a name="examples"></a><span data-ttu-id="7bcd9-788">Exemples</span><span class="sxs-lookup"><span data-stu-id="7bcd9-788">Examples</span></span>

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-skype-for-business-server-2015-pool"></a><span data-ttu-id="7bcd9-789">Déplacement de la configuration annonces du numéro non attribué d’un pool Lync Server 2013 vers un pool 2015 Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="7bcd9-789">Moving the Unassigned Number Announcements Configuration from a Lync Server 2013 Pool to a Skype for Business Server 2015 Pool</span></span>

<span data-ttu-id="7bcd9-790">Dans cet exemple, les annonces de numéro non affectées du pool de destination (Lync Server 2013) sont placées dans la liste de destination (Skype entreprise Server 2015).</span><span class="sxs-lookup"><span data-stu-id="7bcd9-790">This example moves the unassigned number announcements from the source pool (Lync Server 2013) to the destination pool (Skype for Business Server 2015).</span></span>

```PowerShell
Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination SfBS2015Pool.contoso.com
```

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-skype-for-business-server-2015-pool-to-a-lync-server-2013-pool"></a><span data-ttu-id="7bcd9-791">Déplacement de la configuration annonces du numéro non affecté d’un pool Skype entreprise Server 2015 vers un pool Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7bcd9-791">Moving the Unassigned Number Announcements Configuration from a Skype for Business Server 2015 Pool to a Lync Server 2013 Pool</span></span>

<span data-ttu-id="7bcd9-792">Dans cet exemple, les annonces du numéro non affecté sont placées dans la liste de destination (Skype entreprise Server 2015) vers le pool de destination (Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="7bcd9-792">This example moves the unassigned number announcements from the source pool (Skype for Business Server 2015) to the destination pool (Lync Server 2013).</span></span>

```PowerShell
Move-CsAnnouncementConfiguration.ps1 -Source SfBS2015Pool.contoso.com -Destination LS2013Pool.contoso.com
```

## <a name="web-conf-data"></a><span data-ttu-id="7bcd9-793">Web Conf Data</span><span class="sxs-lookup"><span data-stu-id="7bcd9-793">Web Conf Data</span></span>
<span data-ttu-id="7bcd9-794"><a name="WebConfData"> </a></span><span class="sxs-lookup"><span data-stu-id="7bcd9-794"></span></span>

<span data-ttu-id="7bcd9-795">L’outil de données de Web conf permet à un administrateur du logiciel de communication Skype entreprise Server 2015 d’avoir davantage de contrôle sur les données associées aux conférences Web de l’organisateur.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-795">The Web Conf Data Tool allows an administrator of Skype for Business Server 2015 communications software to have more control over the data associated with an organizer's Web conferences.</span></span> <span data-ttu-id="7bcd9-796">Les scénarios incluent la possibilité de supprimer les données de réunion d’un utilisateur spécifiques en fonction de critères d’horodatage.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-796">Scenarios include the ability to delete a specific user's meeting data based on a time stamp criteria.</span></span>

### <a name="description"></a><span data-ttu-id="7bcd9-797">Description</span><span class="sxs-lookup"><span data-stu-id="7bcd9-797">Description</span></span>

<span data-ttu-id="7bcd9-798">Cet outil permet aux administrateurs d’effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="7bcd9-798">This tool allows the administrator to perform the following operations:</span></span>

1. <span data-ttu-id="7bcd9-799">Rechercher les données de conférence web associées à un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-799">Find all Web conferencing data associated with a single user.</span></span>

2. <span data-ttu-id="7bcd9-800">Supprimer les données de conférence web associées à un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-800">Delete all Web conferencing data associated with a single user.</span></span>

3. <span data-ttu-id="7bcd9-801">Supprimer les données de conférence web associées à un utilisateur antérieures à une date donnée.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-801">Delete all Web conferencing data associated with a single user that is older than a certain date.</span></span>

4. <span data-ttu-id="7bcd9-802">Déplacer les données de conférence web associées à un utilisateur lorsque celui-ci est déplacé d’un pool vers un autre.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-802">Move all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span>

> [!NOTE]
> <span data-ttu-id="7bcd9-803">Les outils du kit de ressources pour Lync Server 2010 pris en charge lors du déplacement de toutes les données de conférence Web associées à un utilisateur unique lorsque ce dernier est déplacé d’un pool à un autre.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-803">The Resource Kit Tools for Lync Server 2010 supported moving all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span> <span data-ttu-id="7bcd9-804">Cette fonctionnalité a été supprimée de cet outil et remplacée par le paramètre  **MoveConferenceData**.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-804">That functionality is now deprecated from this tool in favor of the **MoveConferenceData** parameter.</span></span> <span data-ttu-id="7bcd9-805">Pour plus d’informations sur ce paramètre, voir l’applet de connexion [Move-Csuser](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="7bcd9-805">For details about this parameter, see the [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps) cmdlet.</span></span>

<span data-ttu-id="7bcd9-p197">L’outil supprime les données de réunion uniquement pour les réunions inactives. Les réunions actives (ou réunions en sessions) ne peuvent pas être supprimées.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-p197">The tool deletes meeting data only for meetings that are inactive. Active meetings (or meetings in sessions) cannot be deleted.</span></span>

<span data-ttu-id="7bcd9-p198">Cet outil doit être exécuté à partir d’un ordinateur situé dans le même pool que l’utilisateur cible. L’utilisateur dont les données de contenu de réunion sont gérées par cet outil doit être hébergé dans le même pool d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-p198">This tool must be run from a computer that is in the same pool as the target user. The user whose meeting content data is being managed by this tool must be homed in the same user pool.</span></span>

### <a name="output"></a><span data-ttu-id="7bcd9-810">Sortie</span><span class="sxs-lookup"><span data-stu-id="7bcd9-810">Output</span></span>

<span data-ttu-id="7bcd9-811">L’outil génère des résultats pour chacune des opérations :</span><span class="sxs-lookup"><span data-stu-id="7bcd9-811">This tool outputs the results of each of the operations:</span></span>

- <span data-ttu-id="7bcd9-812">Si une requête est exécutée, l’outil génère la liste de tous les dossiers de données des réunions inactives organisées par cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-812">If a query is performed, the tool outputs the list of all inactive meeting data folders that have that user as an organizer.</span></span>

- <span data-ttu-id="7bcd9-813">En cas de suppression, l’outil génère la liste des dossiers de données de toutes les réunions pour lesquelles les données seront supprimées.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-813">If a delete is performed, the tool outputs the list of all meeting data folders whose data will be deleted.</span></span>

### <a name="requirements"></a><span data-ttu-id="7bcd9-814">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="7bcd9-814">Requirements</span></span>

<span data-ttu-id="7bcd9-815">L’outil doit être exécuté dans le même pool qui héberge actuellement l’organisateur.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-815">The tool needs to be run in the same pool where the organizer is currently homed.</span></span>

<span data-ttu-id="7bcd9-816">L’outil doit être exécuté à l’aide de privilèges d’administrateur avec un accès au magasin de fichiers de contenu.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-816">The tool must be run using administrator privileges with access to the Content File Store.</span></span>

### <a name="examples"></a><span data-ttu-id="7bcd9-817">Exemples</span><span class="sxs-lookup"><span data-stu-id="7bcd9-817">Examples</span></span>

<span data-ttu-id="7bcd9-818">Le tableau suivant décrit les paramètres (certains d’entre eux sont utilisés dans les exemples).</span><span class="sxs-lookup"><span data-stu-id="7bcd9-818">The following table describes the parameters, some of which are used in the examples.</span></span>

![Paramètres de l’outil de données Web CONF.](../media/Reskit_2012_Tools_Documentation_Image51.JPG)

```
WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""
```

<span data-ttu-id="7bcd9-p199">L’exemple précédent montre le fonctionnement d’une commande de requête. La sortie d’une telle commande est une liste des dossiers de contenu de réunion affectés par cet outil.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-p199">The preceding example shows how a query command would work. The output of such a command would be a list of all meeting content folders that would be affected by this tool.</span></span>

```
WebConfDataTool.exe /User:user0@contoso.com /Action:delete
```

<span data-ttu-id="7bcd9-p200">L’exemple précédent est une commande de suppression. Cette commande supprime les dossiers des réunions inactives pour cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-p200">The preceding is an example of a delete command. The delete command will remove all inactive meeting folders from this user.</span></span>

### <a name="summary"></a><span data-ttu-id="7bcd9-824">Résumé</span><span class="sxs-lookup"><span data-stu-id="7bcd9-824">Summary</span></span>

<span data-ttu-id="7bcd9-825">Cet outil offre aux administrateurs un contrôle plus précis sur les données de réunion de conférence.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-825">This tool can be a valuable resource to administrators who need more precise control over conference meeting data.</span></span>


