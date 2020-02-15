---
title: Documentation sur les outils du kit de ressources Skype entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/20/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
description: Cette rubrique décrit les outils du kit de ressources Skype entreprise Server 2015, notamment l’objectif de chaque outil, ainsi que des exemples de son utilisation. Le kit de ressources de Skype entreprise Server 2015 facilite les tâches de routine pour les administrateurs qui déploient et gèrent Skype entreprise Server 2015. Par exemple, l’outil Web conf Data peut être utilisé pour contrôler facilement les données téléchargées par les utilisateurs au cours d’une réunion en ligne. L’outil SEFAUtil peut être utilisé pour configurer le transfert d’appel de délégué et la réponse pour les utilisateurs. Nous encourageons les administrateurs informatiques à utiliser ces outils pour gérer plus efficacement Skype entreprise Server 2015.
ms.openlocfilehash: ab43d8e951308fab5a4aefc25d9dad2804ea5d0e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42005989"
---
# <a name="skype-for-business-server-2015-resource-kit-tools-documentation"></a><span data-ttu-id="9d11a-107">Documentation sur les outils du kit de ressources Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="9d11a-107">Skype for Business Server 2015 Resource Kit Tools Documentation</span></span>

<span data-ttu-id="9d11a-108">Cette rubrique décrit les outils du kit de ressources Skype entreprise Server 2015, notamment l’objectif de chaque outil, ainsi que des exemples de son utilisation.</span><span class="sxs-lookup"><span data-stu-id="9d11a-108">This topic describes the tools in the Skype for Business Server 2015 Resource Kit, including the purpose of each tool, and examples of its use.</span></span> <span data-ttu-id="9d11a-109">Le kit de ressources de Skype entreprise Server 2015 facilite les tâches de routine pour les administrateurs qui déploient et gèrent Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9d11a-109">The Skype for Business Server 2015 Resource Kit helps to make routine tasks easier for IT administrators who deploy and manage Skype for Business Server 2015.</span></span> <span data-ttu-id="9d11a-110">Par exemple, l’outil **Web conf Data** peut être utilisé pour contrôler facilement les données téléchargées par les utilisateurs au cours d’une réunion en ligne.</span><span class="sxs-lookup"><span data-stu-id="9d11a-110">For example, the **Web Conf Data** tool can be used to easily control data that is uploaded by users during an online meeting.</span></span> <span data-ttu-id="9d11a-111">L’outil **SEFAUtil** peut être utilisé pour configurer le transfert d’appel de délégué et la réponse pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="9d11a-111">The **SEFAUtil** tool can be used to set up delegate call forwarding and answering for users.</span></span> <span data-ttu-id="9d11a-112">Nous encourageons les administrateurs informatiques à utiliser ces outils pour gérer plus efficacement Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9d11a-112">We encourage IT administrators to use these tools to more effectively manage Skype for Business Server 2015.</span></span>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="9d11a-113">Installation des outils du kit de ressources</span><span class="sxs-lookup"><span data-stu-id="9d11a-113">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="9d11a-114">Pour installer le kit de ressources Skype entreprise Server 2015, téléchargez [OCSReskit. msi](https://www.microsoft.com/download/details.aspx?id=52631) à partir du centre de téléchargement.</span><span class="sxs-lookup"><span data-stu-id="9d11a-114">To install the Skype for Business Server 2015 Resource Kit, download [OCSReskit.msi](https://www.microsoft.com/download/details.aspx?id=52631) from the Download Center.</span></span>

<span data-ttu-id="9d11a-115">Exécutez **OCSResKit. msi** pour effectuer une installation simple.</span><span class="sxs-lookup"><span data-stu-id="9d11a-115">Run **OCSResKit.msi** to do a simple installation.</span></span> <span data-ttu-id="9d11a-116">Le. msi installe tous les outils dans le chemin d’accès suivant : **% Program Files%\Skype for Business Server 2015 \ reskit**.</span><span class="sxs-lookup"><span data-stu-id="9d11a-116">The .msi installs all the tools in the following path: **%Program Files%\Skype for Business Server 2015\ResKit**.</span></span> <span data-ttu-id="9d11a-117">Les outils qui sont des fichiers exécutables autonomes se trouvent dans ce dossier.</span><span class="sxs-lookup"><span data-stu-id="9d11a-117">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="9d11a-118">Les outils qui disposent également de fichiers de prise en charge se trouvent dans leurs propres sous-dossiers.</span><span class="sxs-lookup"><span data-stu-id="9d11a-118">Tools that also have supporting files are in their own subfolders.</span></span>

## <a name="supported-environments"></a><span data-ttu-id="9d11a-119">Environnements pris en charge</span><span class="sxs-lookup"><span data-stu-id="9d11a-119">Supported Environments</span></span>

<span data-ttu-id="9d11a-120">Le kit de ressources Skype entreprise Server 2015 doit être installé sur un serveur qui répond aux spécifications requises pour Skype entreprise Server 2015, généralement utilisé pour exécuter Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9d11a-120">The Skype for Business Server 2015 Resource Kit should be installed on a server that meets the specifications required for Skype for Business Server 2015, usually one being used to run Skype for Business Server 2015.</span></span>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="9d11a-121">Vue d’ensemble des outils du kit de ressources</span><span class="sxs-lookup"><span data-stu-id="9d11a-121">Resource Kit Tools Overview</span></span>

<span data-ttu-id="9d11a-122">La liste suivante répertorie les outils fournis dans le kit de ressources de Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9d11a-122">The following is a list of the tools that are provided in the Skype for Business Server 2015 Resource Kit.</span></span> <span data-ttu-id="9d11a-123">Une description de chaque outil, notamment les conditions requises et des exemples d’utilisation, est décrite dans les sections suivantes.</span><span class="sxs-lookup"><span data-stu-id="9d11a-123">A description of each tool, including the requirements and example usage is covered in the following sections.</span></span>

- [<span data-ttu-id="9d11a-124">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="9d11a-124">ABSConfig</span></span>](resource-kit-tools.md#ABSConfig)

- [<span data-ttu-id="9d11a-125">Moniteur de service de stratégie de bande passante</span><span class="sxs-lookup"><span data-stu-id="9d11a-125">Bandwidth Policy Service Monitor</span></span>](resource-kit-tools.md#bpsm)

- [<span data-ttu-id="9d11a-126">Analyseur d’utilisation de la bande passante</span><span class="sxs-lookup"><span data-stu-id="9d11a-126">Bandwidth Utilization Analyzer</span></span>](resource-kit-tools.md#bua)

- [<span data-ttu-id="9d11a-127">Appeler Parkometer</span><span class="sxs-lookup"><span data-stu-id="9d11a-127">Call Parkometer</span></span>](resource-kit-tools.md#callpark)

- [<span data-ttu-id="9d11a-128">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="9d11a-128">DBAnalyze</span></span>](resource-kit-tools.md#dba)

- [<span data-ttu-id="9d11a-129">Importer les données du service de stockage</span><span class="sxs-lookup"><span data-stu-id="9d11a-129">Import Storage Service Data</span></span>](resource-kit-tools.md#Issd)

- [<span data-ttu-id="9d11a-130">LCSSync</span><span class="sxs-lookup"><span data-stu-id="9d11a-130">LCSSync</span></span>](resource-kit-tools.md#LCSSync)

- [<span data-ttu-id="9d11a-131">Console utilisateur de recherche</span><span class="sxs-lookup"><span data-stu-id="9d11a-131">Lookup User Console</span></span>](resource-kit-tools.md#LUC)

- [<span data-ttu-id="9d11a-132">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="9d11a-132">MsTurnPing</span></span>](resource-kit-tools.md#MsTurnPing)

- [<span data-ttu-id="9d11a-133">Afficheur de configuration réseau</span><span class="sxs-lookup"><span data-stu-id="9d11a-133">Network Configuration Viewer</span></span>](resource-kit-tools.md#NCV)

- [<span data-ttu-id="9d11a-134">Response Group agent Live</span><span class="sxs-lookup"><span data-stu-id="9d11a-134">Response Group Agent Live</span></span>](resource-kit-tools.md#RGAL)

- [<span data-ttu-id="9d11a-135">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="9d11a-135">SEFAUtil</span></span>](resource-kit-tools.md#SEFAUtil)

- [<span data-ttu-id="9d11a-136">SYSPrep. ps1</span><span class="sxs-lookup"><span data-stu-id="9d11a-136">SYSPrep.ps1</span></span>](resource-kit-tools.md#SYSPrep)

- [<span data-ttu-id="9d11a-137">Migration des annonces de numéros non attribués</span><span class="sxs-lookup"><span data-stu-id="9d11a-137">Unassigned Number Announcements Migration</span></span>](resource-kit-tools.md#UNAM)

- [<span data-ttu-id="9d11a-138">Données Web CONF</span><span class="sxs-lookup"><span data-stu-id="9d11a-138">Web Conf Data</span></span>](resource-kit-tools.md#WebConfData)

## <a name="absconfig"></a><span data-ttu-id="9d11a-139">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="9d11a-139">ABSConfig</span></span>
<span data-ttu-id="9d11a-140"><a name="ABSConfig"> </a></span><span class="sxs-lookup"><span data-stu-id="9d11a-140"><a name="ABSConfig"> </a></span></span>

<span data-ttu-id="9d11a-141">L’outil de configuration du service de carnet d’adresses (ABSConfig) est un outil d’administration qui permet aux administrateurs de personnaliser la configuration du service de carnet d’adresses dans Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9d11a-141">The Address Book Service Configuration tool (ABSConfig) is an administrative tool that helps administrators customize Address Book Service configuration in Skype for Business Server 2015.</span></span> <span data-ttu-id="9d11a-142">Cet outil permet également aux administrateurs de Skype entreprise Server 2015 de restaurer les paramètres par défaut du service de carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="9d11a-142">This tool also enables Skype for Business Server 2015 administrators to restore the default Address Book Service settings.</span></span>

### <a name="description"></a><span data-ttu-id="9d11a-143">Description</span><span class="sxs-lookup"><span data-stu-id="9d11a-143">Description</span></span>

<span data-ttu-id="9d11a-144">ABSConfig est une application d’interface utilisateur graphique qui permet aux administrateurs de configurer les attributs des services de domaine Active Directory associés au service de carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="9d11a-144">ABSConfig is a graphical user interface application that enables administrators to configure Active Directory Domain Services attributes that are related to Address Book Service.</span></span>

<span data-ttu-id="9d11a-145">Les principaux scénarios de l’outil sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="9d11a-145">The primary scenarios for the tool are the following:</span></span>

- <span data-ttu-id="9d11a-146">Pour permettre aux administrateurs de mapper les attributs des services de domaine Active Directory aux attributs de Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9d11a-146">To enable administrators to map attributes in Active Directory Domain Services to the attributes for Skype for Business Server 2015.</span></span>

- <span data-ttu-id="9d11a-147">Pour permettre aux administrateurs de spécifier l’attribut des services de domaine Active Directory à inclure ou exclure dans les fichiers du service de carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="9d11a-147">To enable administrators to specify the Active Directory Domain Services attribute to be included or excluded in the Address Book Service files.</span></span>

- <span data-ttu-id="9d11a-148">Pour permettre aux administrateurs de restaurer les paramètres par défaut du service de carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="9d11a-148">To enable administrators to restore default Address Book Service settings.</span></span>

<span data-ttu-id="9d11a-149">L’outil ABSConfig peut être démarré à l’aide du fichier ABSConfig. exe.</span><span class="sxs-lookup"><span data-stu-id="9d11a-149">The ABSConfig tool can be started by using the ABSConfig.exe file.</span></span> <span data-ttu-id="9d11a-150">L’outil s’ouvre sur l’onglet **configurer les attributs** . Ce tableau comporte des options permettant de mapper les attributs des services de domaine Active Directory avec les champs d’attribut de Skype entreprise Server 2015 et de spécifier les utilisateurs à inclure ou à exclure dans les fichiers du service de carnet d’adresses en fonction de filtres d’attributs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="9d11a-150">The tool opens to the **Configure Attributes** tab. This table has options to map Active Directory Domain Services attributes to the attribute fields for Skype for Business Server 2015 and to specify which users to include or exclude in Address Book Service files based on specific attribute filters.</span></span> <span data-ttu-id="9d11a-151">Elle comporte également des options permettant de personnaliser la valeur du numéro de téléphone à inclure dans le fichier de carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="9d11a-151">It also has options to customize which value of the phone number to be included in the Address Book file.</span></span> <span data-ttu-id="9d11a-152">L’option restaurer les paramètres **par défaut** permet aux administrateurs de restaurer les valeurs par défaut des paramètres du service de carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="9d11a-152">The **Restore Defaults** option enables administrators to restore Address Book Service settings to default values.</span></span>

> [!NOTE]
> <span data-ttu-id="9d11a-153">Le remappage des attributs AD sur différents noms de champs OC fonctionnera uniquement pour le téléchargement de fichier de carnet d’adresses et n’est pas pris en charge par la requête Web de carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="9d11a-153">Re-mapping of AD attributes to different OC Field Names will only work for Address Book File Download, and is not supported by Address Book Web Query.</span></span>

### <a name="output"></a><span data-ttu-id="9d11a-154">Output</span><span class="sxs-lookup"><span data-stu-id="9d11a-154">Output</span></span>

<span data-ttu-id="9d11a-155">ABSConfig stocke la configuration du service de carnet d’adresses dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="9d11a-155">ABSConfig stores the Address Book Service configuration in the database.</span></span>

```console
Path: %ProgramFiles%\Skype for Business Server 2015\Reskit
```

### <a name="purpose"></a><span data-ttu-id="9d11a-156">Objectif</span><span class="sxs-lookup"><span data-stu-id="9d11a-156">Purpose</span></span>

<span data-ttu-id="9d11a-157">ABSConfig offre un moyen rapide et simple de personnaliser le service de carnet d’adresses Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9d11a-157">ABSConfig provides a quick and easy way to customize Skype for Business Server 2015 Address Book Service.</span></span>

### <a name="requirements"></a><span data-ttu-id="9d11a-158">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="9d11a-158">Requirements</span></span>

#### <a name="computer"></a><span data-ttu-id="9d11a-159">Ordinateur</span><span class="sxs-lookup"><span data-stu-id="9d11a-159">Computer</span></span>

<span data-ttu-id="9d11a-160">ABSConfig ne peut être exécuté qu’à partir d’un ordinateur joint à un domaine sur lequel Skype entreprise Server 2015 est installé.</span><span class="sxs-lookup"><span data-stu-id="9d11a-160">ABSConfig can be run only from a domain-joined computer that has Skype for Business Server 2015 installed.</span></span> <span data-ttu-id="9d11a-161">Dans le cas de Skype entreprise Server 2015, Enterprise Edition, cet outil peut être exécuté sur tous les serveurs frontaux pour lesquels le service de carnet d’adresses est activé lors de l’installation.</span><span class="sxs-lookup"><span data-stu-id="9d11a-161">In the case of Skype for Business Server 2015, Enterprise Edition, this tool can be run on any Front End servers that have the Address Book Service enabled during setup.</span></span>

#### <a name="network"></a><span data-ttu-id="9d11a-162">Réseau</span><span class="sxs-lookup"><span data-stu-id="9d11a-162">Network</span></span>

<span data-ttu-id="9d11a-163">L’ordinateur doit être en mesure de se connecter au pool frontal et à la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="9d11a-163">The computer should be able to connect to the Front End pool and back-end database.</span></span>

#### <a name="software"></a><span data-ttu-id="9d11a-164">Logiciels</span><span class="sxs-lookup"><span data-stu-id="9d11a-164">Software</span></span>

<span data-ttu-id="9d11a-165">Les composants logiciels suivants doivent être installés avant d’exécuter l’outil ABSConfig :</span><span class="sxs-lookup"><span data-stu-id="9d11a-165">The following software components must be installed before running the ABSConfig tool:</span></span>

- <span data-ttu-id="9d11a-166">Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="9d11a-166">Skype for Business Server 2015</span></span>

#### <a name="users"></a><span data-ttu-id="9d11a-167">Utilisateurs</span><span class="sxs-lookup"><span data-stu-id="9d11a-167">Users</span></span>

<span data-ttu-id="9d11a-168">Administrateurs disposant des autorisations nécessaires pour mettre à jour le déploiement de Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9d11a-168">Administrators who have the permissions required to update the Skype for Business Server 2015 deployment.</span></span>

### <a name="examples"></a><span data-ttu-id="9d11a-169">範例</span><span class="sxs-lookup"><span data-stu-id="9d11a-169">Examples</span></span>

<span data-ttu-id="9d11a-170">ABSConfig peut être démarré en tapant **ABSConfig. exe** à une invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="9d11a-170">ABSConfig can be started by typing **ABSConfig.exe** at a command prompt.</span></span> <span data-ttu-id="9d11a-171">L’interface utilisateur de l’outil ABSConfig est illustrée ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="9d11a-171">Shown below is the ABSConfig tool user interface.</span></span>

![L’outil ABSConfig. exe.](../media/Reskit_2012_Tools_Documentation_ABSConfig.JPG)

### <a name="summary"></a><span data-ttu-id="9d11a-173">Résumé</span><span class="sxs-lookup"><span data-stu-id="9d11a-173">Summary</span></span>

<span data-ttu-id="9d11a-174">L’outil ABSConfig fournit aux administrateurs un outil rapide et facile à utiliser pour personnaliser le service de carnet d’adresses Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9d11a-174">The ABSConfig tool provides administrators a quick and easy to use tool to customize Skype for Business Server 2015 Address Book Service.</span></span>

## <a name="bandwidth-policy-service-monitor"></a><span data-ttu-id="9d11a-175">Moniteur de service de stratégie de bande passante</span><span class="sxs-lookup"><span data-stu-id="9d11a-175">Bandwidth Policy Service Monitor</span></span>
<span data-ttu-id="9d11a-176"><a name="bpsm"> </a></span><span class="sxs-lookup"><span data-stu-id="9d11a-176"><a name="bpsm"> </a></span></span>

<span data-ttu-id="9d11a-177">L’outil Moniteur de service de stratégie de bande passante permet aux administrateurs d’afficher la liste des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="9d11a-177">The Bandwidth Policy Service Monitor tool is intended to allow administrators to view a list of the following:</span></span>

1. <span data-ttu-id="9d11a-178">Tous les services de stratégie de bande passante de Skype entreprise Server 2015 configurés (authentification et cœur) dans la topologie</span><span class="sxs-lookup"><span data-stu-id="9d11a-178">All the configured Skype for Business Server 2015 Bandwidth Policy services (Authentication and Core) in the topology</span></span>

2. <span data-ttu-id="9d11a-179">Les connexions que chaque service effectue à d’autres services de stratégie de bande passante et aux serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="9d11a-179">The connections that each service makes to other Bandwidth Policy services and to the Edge servers</span></span>

3. <span data-ttu-id="9d11a-180">Tous les liens configurés dans le document de configuration réseau et l’utilisation de la bande passante en temps réel comme indiqué par chacun des services de stratégie de bande passante</span><span class="sxs-lookup"><span data-stu-id="9d11a-180">All the links that are configured in the Network configuration document and real-time bandwidth usage as reported by each of the Bandwidth Policy services</span></span>

### <a name="description"></a><span data-ttu-id="9d11a-181">Description</span><span class="sxs-lookup"><span data-stu-id="9d11a-181">Description</span></span>

<span data-ttu-id="9d11a-182">L’outil Moniteur de service de stratégie de bande passante est implémenté en tant qu’application basée sur une interface utilisateur graphique.</span><span class="sxs-lookup"><span data-stu-id="9d11a-182">The Bandwidth Policy Service Monitor tool is implemented as a GUI-based application.</span></span> <span data-ttu-id="9d11a-183">Les administrateurs démarrent l’outil en exécutant PDPMonUI. exe.</span><span class="sxs-lookup"><span data-stu-id="9d11a-183">Administrators start the tool by running PDPMonUI.exe.</span></span>

<span data-ttu-id="9d11a-184">Lorsque l’outil démarre, il tente de découvrir la liste des services de stratégie de bande passante dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="9d11a-184">When the tool starts, it attempts to discover the list of Bandwidth Policy services in the topology.</span></span> <span data-ttu-id="9d11a-185">Une fois la mise à jour initiale terminée, le volet à gauche de la fenêtre est renseigné avec une liste de services qui sont regroupés par les clusters auxquels ils appartiennent.</span><span class="sxs-lookup"><span data-stu-id="9d11a-185">After the initial update is done, the pane to the left of the window is populated with a list of services that are grouped by the clusters that they belong to.</span></span>

<span data-ttu-id="9d11a-186">Lorsque les administrateurs sélectionnent un service de stratégie de bande passante particulier, le volet de droite affiche les informations relatives à ce service particulier.</span><span class="sxs-lookup"><span data-stu-id="9d11a-186">When administrators select a particular Bandwidth Policy Service, the pane on the right displays the information about that particular service.</span></span> <span data-ttu-id="9d11a-187">Ce volet comporte également deux onglets principaux qui affichent des informations.</span><span class="sxs-lookup"><span data-stu-id="9d11a-187">That pane also has two main tabs that display information.</span></span>

#### <a name="machine-info-tab"></a><span data-ttu-id="9d11a-188">Onglet Infos ordinateur</span><span class="sxs-lookup"><span data-stu-id="9d11a-188">Machine Info Tab</span></span>

<span data-ttu-id="9d11a-189">L’onglet **infos ordinateur** affiche les détails du service de stratégie de bande passante sélectionné et la liste et l’état de toutes les connexions établies par le service de stratégie de bande passante sélectionné à d’autres services.</span><span class="sxs-lookup"><span data-stu-id="9d11a-189">The **Machine Info** tab shows the details of the Bandwidth Policy Service that is selected and the list and state of all the connections that are made by the selected Bandwidth Policy Service to other services.</span></span>

#### <a name="topology-info-tab"></a><span data-ttu-id="9d11a-190">Onglet informations sur la topologie</span><span class="sxs-lookup"><span data-stu-id="9d11a-190">Topology Info Tab</span></span>

<span data-ttu-id="9d11a-191">L’onglet **informations sur la topologie** affiche une liste de tous les liens configurés dans les paramètres de configuration du réseau.</span><span class="sxs-lookup"><span data-stu-id="9d11a-191">The **Topology Info** tab shows a list of all the links that are configured in the Network configuration settings.</span></span> <span data-ttu-id="9d11a-192">Pour chaque lien, la capacité de bande passante audio et vidéo est affichée.</span><span class="sxs-lookup"><span data-stu-id="9d11a-192">For each link, the audio and video bandwidth capacity is displayed.</span></span> <span data-ttu-id="9d11a-193">En outre, la bande passante actuellement utilisée est affichée, à la fois en Kbits/s et en pourcentage de la capacité.</span><span class="sxs-lookup"><span data-stu-id="9d11a-193">Additionally, the currently utilized bandwidth is displayed, both in Kbps and as a percentage of the capacity.</span></span> <span data-ttu-id="9d11a-194">L’outil utilise un codage en couleurs pour mettre en surbrillance les liens dont l’utilisation est proche de la capacité, ce qui permet aux administrateurs d’isoler rapidement ces liens.</span><span class="sxs-lookup"><span data-stu-id="9d11a-194">The tool uses color-coding to highlight links that have utilization that is close to the capacity—this allows administrators to quickly isolate such links.</span></span>

> [!NOTE]
>  <span data-ttu-id="9d11a-195">Si l’outil Moniteur de service de stratégie de bande passante rencontre une défaillance lorsqu’il se connecte à l’un des services de stratégie de bande passante configurés, les informations des onglets **infos ordinateur** et informations sur la **topologie** ne seront pas renseignées.</span><span class="sxs-lookup"><span data-stu-id="9d11a-195">If the Bandwidth Policy Service Monitor tool experiences failure when it connects to any of the configured Bandwidth Policy services, the information in the **Machine Info** and the **Topology Info** tabs won't be populated.</span></span> <span data-ttu-id="9d11a-196">Toutefois, il est possible que l’outil se connecte à l’origine, mais perd sa connexion au service.</span><span class="sxs-lookup"><span data-stu-id="9d11a-196">However, it is possible that the tool might connect initially but subsequently lose its connection to the service.</span></span> <span data-ttu-id="9d11a-197">Dans ce cas, les administrateurs peuvent voir des informations périmées.</span><span class="sxs-lookup"><span data-stu-id="9d11a-197">In such cases, administrators might see outdated information.</span></span> <span data-ttu-id="9d11a-198">Il existe un **dernier horodatage mis à jour** sur chacun des onglets qui permet aux administrateurs de savoir quand les données ont été mises à jour pour un service de stratégie de bande passante particulier.</span><span class="sxs-lookup"><span data-stu-id="9d11a-198">There is a **Last Updated** time stamp on each of the tabs that can allow administrators to see when the data was last updated for a particular Bandwidth Policy Service.</span></span>

### <a name="output"></a><span data-ttu-id="9d11a-199">Output</span><span class="sxs-lookup"><span data-stu-id="9d11a-199">Output</span></span>

<span data-ttu-id="9d11a-200">Il n’y a pas de sortie de ligne de commande ; la sortie du programme est contenue dans l’interface utilisateur graphique principale.</span><span class="sxs-lookup"><span data-stu-id="9d11a-200">There is no command-line output; the program output is contained within the main graphical user interface (GUI).</span></span>

### <a name="purpose"></a><span data-ttu-id="9d11a-201">Objectif</span><span class="sxs-lookup"><span data-stu-id="9d11a-201">Purpose</span></span>

<span data-ttu-id="9d11a-202">L’objectif de l’outil Moniteur de service de stratégie de bande passante est de permettre aux administrateurs de visualiser l’état de chacun des services de stratégie de bande passante définis dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="9d11a-202">The purpose of the Bandwidth Policy Service Monitor tool is to allow administrators visibility into the state of each of the Bandwidth Policy services that are defined in the topology.</span></span> <span data-ttu-id="9d11a-203">En outre, les administrateurs peuvent voir l’utilisation de la bande passante en temps réel pour tous les liens définis dans le document de configuration du réseau.</span><span class="sxs-lookup"><span data-stu-id="9d11a-203">In addition, administrators can see real-time bandwidth usage for all the links that are defined in the Network configuration document.</span></span>

### <a name="requirements"></a><span data-ttu-id="9d11a-204">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="9d11a-204">Requirements</span></span>

<span data-ttu-id="9d11a-205">L’outil Moniteur de service de stratégie de bande passante doit être exécuté sur un ordinateur qui fait partie de la topologie Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="9d11a-205">The Bandwidth Policy Service Monitor tool needs to be run on a computer that is part of the Skype for Business Server topology.</span></span>

### <a name="summary"></a><span data-ttu-id="9d11a-206">Résumé</span><span class="sxs-lookup"><span data-stu-id="9d11a-206">Summary</span></span>

<span data-ttu-id="9d11a-207">L’outil Moniteur de service de stratégie de bande passante peut être une ressource précieuse pour les administrateurs afin qu’ils puissent inspecter l’état de tous les services de stratégie de bande passante dans la topologie, et plus important, ils peuvent obtenir une utilisation en temps réel de la bande passante pour les liens qui sont défini dans les paramètres de configuration réseau.</span><span class="sxs-lookup"><span data-stu-id="9d11a-207">The Bandwidth Policy Service Monitor tool can be a valuable resource to administrators so they can inspect the state of all the Bandwidth Policy services in the topology—and more importantly—they can obtain real-time bandwidth utilization for the links that are defined in the Network configuration settings.</span></span>

## <a name="bandwidth-utilization-analyzer"></a><span data-ttu-id="9d11a-208">Analyseur d’utilisation de la bande passante</span><span class="sxs-lookup"><span data-stu-id="9d11a-208">Bandwidth Utilization Analyzer</span></span>
<span data-ttu-id="9d11a-209"><a name="bua"> </a></span><span class="sxs-lookup"><span data-stu-id="9d11a-209"><a name="bua"> </a></span></span>

<span data-ttu-id="9d11a-210">L’analyseur d’utilisation de la bande passante est un outil qui crée des rapports sur les différentes vues de la consommation de bande passante par les points de terminaison UC sur les liaisons de réseau étendu dans le réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="9d11a-210">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network.</span></span> <span data-ttu-id="9d11a-211">Ces rapports peuvent être utilisés pour comprendre le modèle de consommation de bande passante actuel et pour faciliter la planification de la capacité de bande passante.</span><span class="sxs-lookup"><span data-stu-id="9d11a-211">These reports can be used to understand the current bandwidth consumption pattern and to aid in bandwidth capacity planning.</span></span>

### <a name="description"></a><span data-ttu-id="9d11a-212">Description</span><span class="sxs-lookup"><span data-stu-id="9d11a-212">Description</span></span>

<span data-ttu-id="9d11a-213">L’analyseur d’utilisation de la bande passante est implémenté en tant qu’application basée sur une interface utilisateur graphique.</span><span class="sxs-lookup"><span data-stu-id="9d11a-213">Bandwidth Utilization Analyzer is implemented as a GUI-based application.</span></span> <span data-ttu-id="9d11a-214">Cet outil génère des rapports spécifiquement pour l’utilisation audio sur le réseau et vous aide à planifier la capacité.</span><span class="sxs-lookup"><span data-stu-id="9d11a-214">This tool generates reports specifically for audio utilization across the network and helps with capacity planning.</span></span> <span data-ttu-id="9d11a-215">Elle effectue également une itération sur la capacité de bande passante affectée à différents liens.</span><span class="sxs-lookup"><span data-stu-id="9d11a-215">It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

### <a name="output"></a><span data-ttu-id="9d11a-216">Output</span><span class="sxs-lookup"><span data-stu-id="9d11a-216">Output</span></span>

<span data-ttu-id="9d11a-217">Bandwidth utilization Analyzer fournit des tracés graphiques de la capacité de bande passante et de l’utilisation de l’audio pour toutes les liaisons de réseau étendu configurées dans le système.</span><span class="sxs-lookup"><span data-stu-id="9d11a-217">Bandwidth Utilization Analyzer provides graphic al plots of bandwidth capacity and utilization for audio for all the WAN links that are configured in the system.</span></span>

### <a name="purpose"></a><span data-ttu-id="9d11a-218">Objectif</span><span class="sxs-lookup"><span data-stu-id="9d11a-218">Purpose</span></span>

<span data-ttu-id="9d11a-219">Dans tout déploiement vocal et vidéo, il est essentiel de surveiller et de comprendre la tendance de l’utilisation de la bande passante du trafic multimédia sur le réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="9d11a-219">In any voice and video deployment, it's critical to monitor and understand the trend of bandwidth utilization of media traffic across the enterprise network.</span></span> <span data-ttu-id="9d11a-220">L’outil d’analyse de l’utilisation de la bande passante permet à un administrateur d’atteindre le même objectif.</span><span class="sxs-lookup"><span data-stu-id="9d11a-220">The Bandwidth Utilization Analyzer tool allows an administrator to achieve just that.</span></span> <span data-ttu-id="9d11a-221">Cet outil effectue les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="9d11a-221">This tool does the following:</span></span>

- <span data-ttu-id="9d11a-222">Génère des rapports spécifiques pour l’utilisation audio sur le réseau</span><span class="sxs-lookup"><span data-stu-id="9d11a-222">Generates specific reports for audio utilization across the network</span></span>

- <span data-ttu-id="9d11a-223">Permet une planification et une itération de capacité plus efficaces sur la capacité de bande passante affectée à différents liens</span><span class="sxs-lookup"><span data-stu-id="9d11a-223">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="9d11a-224">Bandwidth utilization Analyzer peut générer des placettes graphiques de capacité de bande passante et de rapports d’utilisation ; Il s’agit des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="9d11a-224">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and utilization reports; they are as follows:</span></span>

- <span data-ttu-id="9d11a-225">Toutes les liaisons de réseau étendu dans le réseau d’entreprise</span><span class="sxs-lookup"><span data-stu-id="9d11a-225">All the WAN links in the enterprise network</span></span>

- <span data-ttu-id="9d11a-226">Filtré par les liaisons WAN sélectionnées qui ont été choisies</span><span class="sxs-lookup"><span data-stu-id="9d11a-226">Filtered by selected WAN links that have been chosen</span></span>

- <span data-ttu-id="9d11a-227">Filtrés par des liaisons de réseau étendu ayant dépassé la capacité de liaison</span><span class="sxs-lookup"><span data-stu-id="9d11a-227">Filtered by WAN links that have exceeded link capacity</span></span>

- <span data-ttu-id="9d11a-228">Filtrés par des liaisons de réseau étendu qui ont été sous-utilisant la bande passante approvisionnée</span><span class="sxs-lookup"><span data-stu-id="9d11a-228">Filtered by WAN links that have been under-utilizing the provisioned bandwidth</span></span>

- <span data-ttu-id="9d11a-229">Filtrer par les liaisons de réseau étendu qui ont atteint des niveaux critiques (une utilisation de bande passante supérieure à 90% de la capacité de bande passante de la liaison de réseau étendu)</span><span class="sxs-lookup"><span data-stu-id="9d11a-229">Filter by WAN links that have been reaching critical levels (a bandwidth utilization that is greater than 90% of bandwidth capacity of the WAN link)</span></span>

- <span data-ttu-id="9d11a-230">Filtré par type de lien WAN — liaisons de sites réseau, liens interrégionaux et liens au sein d’un site</span><span class="sxs-lookup"><span data-stu-id="9d11a-230">Filtered by WAN link type—network-site links, interregional links, and links within a site</span></span>

- <span data-ttu-id="9d11a-231">Filtré par région réseau</span><span class="sxs-lookup"><span data-stu-id="9d11a-231">Filtered by network region</span></span>

#### <a name="applications"></a><span data-ttu-id="9d11a-232">Applications</span><span class="sxs-lookup"><span data-stu-id="9d11a-232">Applications</span></span>

<span data-ttu-id="9d11a-233">L’analyseur d’utilisation de la bande passante comporte les deux applications suivantes (outils) :</span><span class="sxs-lookup"><span data-stu-id="9d11a-233">Bandwidth Utilization Analyzer has the following two applications (tools):</span></span>

- <span data-ttu-id="9d11a-234">**WanLinkLogCollector. exe** cet outil permet à son utilisateur d’entrer les informations requises.</span><span class="sxs-lookup"><span data-stu-id="9d11a-234">**WanLinkLogCollector.exe** This tool enables its user to input the required information.</span></span>

- <span data-ttu-id="9d11a-235">**BandwidthUtilizationAnalyzer. xlsm** un rapport de logiciel de feuille de calcul Microsoft Excel est automatiquement lancé par WanLinkLogCollector. exe.</span><span class="sxs-lookup"><span data-stu-id="9d11a-235">**BandwidthUtilizationAnalyzer.xlsm** A Microsoft Excel spreadsheet software report is automatically launched by WanLinkLogCollector.exe.</span></span> <span data-ttu-id="9d11a-236">Cette application permet à l’utilisateur d’appliquer des filtres au rapport, comme indiqué plus loin dans cet article.</span><span class="sxs-lookup"><span data-stu-id="9d11a-236">This application allows the user to apply filters to the report as shown later in this article.</span></span>

#### <a name="phases-of-using-bandwidth-utilization-analyzer"></a><span data-ttu-id="9d11a-237">Phases de l’utilisation de l’analyseur d’utilisation de la bande passante</span><span class="sxs-lookup"><span data-stu-id="9d11a-237">Phases of Using Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="9d11a-238">Il existe deux phases lors de l’utilisation de l’analyseur d’utilisation de la bande passante :</span><span class="sxs-lookup"><span data-stu-id="9d11a-238">There are two phases when using Bandwidth Utilization Analyzer:</span></span>

- <span data-ttu-id="9d11a-239">Collecter les journaux, qui sont exécutés à l’aide de WanLinkLogCollector. exe</span><span class="sxs-lookup"><span data-stu-id="9d11a-239">Collect logs, which is performed by using WanLinkLogCollector.exe</span></span>

- <span data-ttu-id="9d11a-240">Personnaliser des rapports, qui est effectué à l’aide de BandwidthUtilizationAnalyzer. xlsm</span><span class="sxs-lookup"><span data-stu-id="9d11a-240">Customize reports, which is performed by using BandwidthUtilizationAnalyzer.xlsm</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="9d11a-241">Il est vivement recommandé que BandwidthUtilizationAnalyzer. xlsm ne soit pas lancé manuellement par les utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="9d11a-241">We strongly recommend that BandwidthUtilizationAnalyzer.xlsm not be manually launched by end users.</span></span>

#### <a name="starting-bandwidth-utilization-analyzer"></a><span data-ttu-id="9d11a-242">Démarrage de l’analyseur d’utilisation de la bande passante</span><span class="sxs-lookup"><span data-stu-id="9d11a-242">Starting Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="9d11a-243">Démarrez WanLinkLogCollector. exe à l’invite de commandes ou à l’aide de l’Explorateur Windows.</span><span class="sxs-lookup"><span data-stu-id="9d11a-243">Start WanLinkLogCollector.exe at the command prompt or by using Windows Explorer.</span></span>

 <span data-ttu-id="9d11a-244">**Utilisation de WanLinkLogCollector. exe**</span><span class="sxs-lookup"><span data-stu-id="9d11a-244">**Using WanLinkLogCollector.exe**</span></span>

<span data-ttu-id="9d11a-245">Il existe trois étapes à suivre pour utiliser WanLinkLogCollector. exe :</span><span class="sxs-lookup"><span data-stu-id="9d11a-245">There are three steps to using WanLinkLogCollector.exe:</span></span>

1. <span data-ttu-id="9d11a-246">**Journalisation de la chronologie** Fournir la chronologie pour laquelle le rapport doit être généré</span><span class="sxs-lookup"><span data-stu-id="9d11a-246">**Log the timeline** Provide the timeline that the report needs to be generated for</span></span>

2. <span data-ttu-id="9d11a-247">**Spécifier les répertoires de fichiers** Fournir des informations sur l’emplacement des fichiers</span><span class="sxs-lookup"><span data-stu-id="9d11a-247">**Specify the file directories** Provide file location information</span></span>

3. <span data-ttu-id="9d11a-248">**Collecter les journaux et lancer la visionneuse de rapports** Exécuter la commande pour générer le rapport</span><span class="sxs-lookup"><span data-stu-id="9d11a-248">**Collect the logs and launch the report viewer** Execute the command to generate the report</span></span>

#### <a name="step-1---log-the-timeline"></a><span data-ttu-id="9d11a-249">Étape 1 : journalisation de la chronologie</span><span class="sxs-lookup"><span data-stu-id="9d11a-249">Step 1 - Log the timeline</span></span>

<span data-ttu-id="9d11a-250">La journalisation de la chronologie permet à l’utilisateur de l’outil de spécifier les éléments suivants, comme illustré dans la figure ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="9d11a-250">Logging the timeline allows the tool user to specify the following as shown in the figure below.</span></span>

1. <span data-ttu-id="9d11a-251">**Date de début** Il s’agit de la date de début de la chronologie pour laquelle le rapport doit être généré ; par exemple, le 1er août 2010.</span><span class="sxs-lookup"><span data-stu-id="9d11a-251">**Start date** This is the start date of the timeline that the report is to be generated for; for example, August 1, 2010.</span></span>

2. <span data-ttu-id="9d11a-252">**Date de fin** Il s’agit de la date de fin de la chronologie pour laquelle le rapport doit être généré ; par exemple, le 30 septembre 2010.</span><span class="sxs-lookup"><span data-stu-id="9d11a-252">**End date** This is the end date of the timeline that the report is to be generated for; for example, September 30, 2010.</span></span>

     ![Dates de début et de fin dans l’utilisation de la bande passante](../media/Reskit_2012_Tools_Documentation_Image4.jpg)

#### <a name="step-2---specify-the-file-directories"></a><span data-ttu-id="9d11a-254">Étape 2 : spécification des répertoires de fichiers</span><span class="sxs-lookup"><span data-stu-id="9d11a-254">Step 2 - Specify the file directories</span></span>

<span data-ttu-id="9d11a-255">Les répertoires de fichiers suivants peuvent être spécifiés par l’utilisateur comme indiqué.</span><span class="sxs-lookup"><span data-stu-id="9d11a-255">The following file directories can be specified by the user as shown.</span></span>

- <span data-ttu-id="9d11a-256">**Emplacement des fichiers journaux du serveur** Emplacement du dossier dans lequel sont stockés les journaux du serveur de stratégie de bande passante.</span><span class="sxs-lookup"><span data-stu-id="9d11a-256">**Server log files location** The folder location where Bandwidth policy server logs are stored.</span></span> <span data-ttu-id="9d11a-257">Il s’agit \<\> \\<généralement du \AppServerFiles\PDP. choix de\>Fe</span><span class="sxs-lookup"><span data-stu-id="9d11a-257">This is typically in \<fileserver\>\\<choice of FE\>\AppServerFiles\PDP.</span></span>

- <span data-ttu-id="9d11a-258">**Emplacement de stockage des fichiers temporaires** Emplacement du fichier temporaire dans lequel les fichiers intermédiaires sont stockés pendant la génération du rapport.</span><span class="sxs-lookup"><span data-stu-id="9d11a-258">**Temporary file storage location** The temporary file location where intermediate files are stored while the report is being generated.</span></span>

    ![Répertoires de fichiers dans l’utilisation de la bande passante anal](../media/Reskit_2012_Tools_Documentation_Image5.jpg)

    > [!NOTE]
    > <span data-ttu-id="9d11a-260">Assurez-vous qu’un accès suffisant aux journaux du serveur et au dossier de magasin de fichiers temporaire est fourni à l’utilisateur de l’outil.</span><span class="sxs-lookup"><span data-stu-id="9d11a-260">Ensure that sufficient file access to the server logs and the temporary file store folder is provided to the tool user.</span></span>

#### <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a><span data-ttu-id="9d11a-261">Étape 3 : collecte des journaux et démarrage de la visionneuse de rapports</span><span class="sxs-lookup"><span data-stu-id="9d11a-261">Step 3 - Collect the logs and start the report viewer</span></span>

<span data-ttu-id="9d11a-262">Pour collecter les journaux et démarrer la visionneuse de rapports, cliquez sur **exécuter** comme indiqué ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="9d11a-262">To collect the logs and start the report viewer, click **Execute** as shown below.</span></span> <span data-ttu-id="9d11a-263">Cette étape collecte les données requises.</span><span class="sxs-lookup"><span data-stu-id="9d11a-263">This step collects the required data.</span></span>

![Collecte de données dans l’utilisation de la bande passante](../media/Reskit_2012_Tools_Documentation_Image6.jpg)

<span data-ttu-id="9d11a-265">Une fois la validation d’entrée réussie, le message ci-dessous s’affiche.</span><span class="sxs-lookup"><span data-stu-id="9d11a-265">When the input validation is successful, the message shown below is displayed.</span></span>

![Enregistre la notification collectée dans la bande passante utili](../media/Reskit_2012_Tools_Documentation_Image7.jpg)

<span data-ttu-id="9d11a-267">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="9d11a-267">Click **OK**.</span></span> <span data-ttu-id="9d11a-268">BandwidthUtilizationAnalyzer. xlsm démarre automatiquement.</span><span class="sxs-lookup"><span data-stu-id="9d11a-268">BandwidthUtilizationAnalyzer.xlsm is automatically started.</span></span> <span data-ttu-id="9d11a-269">Suivez les instructions indiquées dans la boîte de message.</span><span class="sxs-lookup"><span data-stu-id="9d11a-269">Follow the instructions in the message box.</span></span> <span data-ttu-id="9d11a-270">Pour plus d’informations, reportez-vous **à utilisation de BandwidthUtilizationAnalyzer. xlsm** dans la section suivante.</span><span class="sxs-lookup"><span data-stu-id="9d11a-270">For details, see **Using BandwidthUtilizationAnalyzer.xlsm** in the next section.</span></span>


### <a name="using-bandwidthutilizationanalyzerxlsm"></a><span data-ttu-id="9d11a-271">Utilisation de BandwidthUtilizationAnalyzer. xlsm</span><span class="sxs-lookup"><span data-stu-id="9d11a-271">Using BandwidthUtilizationAnalyzer.xlsm</span></span>

1. <span data-ttu-id="9d11a-272">Lorsque BandwidthUtilizationAnalyzer. xlsm démarre automatiquement, cliquez sur **Actualiser** comme indiqué ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="9d11a-272">When BandwidthUtilizationAnalyzer.xlsm is automatically started, click **Refresh** as shown below.</span></span>

     ![BandwidthUtilizationAnalyzer. xlsm](../media/Reskit_2012_Tools_Documentation_Image8.jpg)

2. <span data-ttu-id="9d11a-274">Lors de l’ouverture d’un dossier de fichiers, sélectionnez Consolidated. csv à partir de l’emplacement spécifié dans la zone de message, comme indiqué ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="9d11a-274">When a file folder is opened, select consolidated.csv from the location that is specified in the message box as shown below.</span></span> <span data-ttu-id="9d11a-275">Il affiche également l’emplacement **C:\temp**.</span><span class="sxs-lookup"><span data-stu-id="9d11a-275">It also shows the location as **C:\Temp**.</span></span>

     ![Ouverture d’un dossier dans BandwidthUtilizationAnalyzer.](../media/Reskit_2012_Tools_Documentation_Image9.jpg)

3. <span data-ttu-id="9d11a-277">Cliquez sur **Importer**.</span><span class="sxs-lookup"><span data-stu-id="9d11a-277">Click **Import**.</span></span>

4. <span data-ttu-id="9d11a-278">Le tracé graphique est généré automatiquement.</span><span class="sxs-lookup"><span data-stu-id="9d11a-278">The graphical plot is automatically generated.</span></span> <span data-ttu-id="9d11a-279">Elle est disponible lorsque le pointeur de travail en arrière-plan disparaît.</span><span class="sxs-lookup"><span data-stu-id="9d11a-279">It is available when the working-in-the-background pointer disappears.</span></span>

     ![Application de filtres en mode état.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

#### <a name="applying-filters-to-the-report-view"></a><span data-ttu-id="9d11a-281">Application de filtres à l’affichage de rapport</span><span class="sxs-lookup"><span data-stu-id="9d11a-281">Applying Filters to the Report View</span></span>

<span data-ttu-id="9d11a-282">Les filtres qui peuvent être appliqués à l’affichage de rapport comme indiqué ci-dessous sont décrits comme suit :</span><span class="sxs-lookup"><span data-stu-id="9d11a-282">The filters that can be applied to the report view as shown below are described as follows:</span></span>

![Application de filtres en mode état.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

1. <span data-ttu-id="9d11a-284">**Name (nom** ) Filtrer par liaisons WAN (le filtre se trouve sur le côté droit du graphique). Le préfixe indique les types de liens suivants : consultez la zone vertical (bleu) :</span><span class="sxs-lookup"><span data-stu-id="9d11a-284">**Name** Filter by WAN links (the filter is on the right side of the graph).The prefix denotes the following link types; see the vertical (blue) box:</span></span>

   - <span data-ttu-id="9d11a-285">**Site S** Liaison WAN entre un site réseau et une région réseau</span><span class="sxs-lookup"><span data-stu-id="9d11a-285">**S Site** The WAN link from a network site to a network region</span></span>

   - <span data-ttu-id="9d11a-286">**Est inter-site** La liaison de réseau étendu entre deux sites réseau</span><span class="sxs-lookup"><span data-stu-id="9d11a-286">**IS Inter-Site** The WAN link between two network sites</span></span>

   - <span data-ttu-id="9d11a-287">**R inter-région** La liaison de réseau étendu entre deux régions réseau</span><span class="sxs-lookup"><span data-stu-id="9d11a-287">**R Inter-Region** The WAN link between two network region</span></span>

2. <span data-ttu-id="9d11a-288">**Limite dépassée** Filtrer par des liaisons de réseau étendu dont l’utilisation de la bande passante est supérieure à la capacité de bande passante</span><span class="sxs-lookup"><span data-stu-id="9d11a-288">**Exceeded limit** Filter by WAN links whose bandwidth utilization is more than the bandwidth capacity</span></span>

3. <span data-ttu-id="9d11a-289">**Niveaux critiques** Filtrer par des liaisons de réseau étendu dont l’utilisation de la bande passante atteint 90% ou plus de la capacité de bande passante</span><span class="sxs-lookup"><span data-stu-id="9d11a-289">**Critical levels** Filter by WAN links whose bandwidth utilization has reached 90% or more than the bandwidth capacity</span></span>

4. <span data-ttu-id="9d11a-290">**Sous-utilisés** Filtrer par des liaisons de réseau étendu dont l’utilisation de la bande passante est inférieure à 25% de la capacité de bande passante</span><span class="sxs-lookup"><span data-stu-id="9d11a-290">**Under-utilized** Filter by WAN links whose bandwidth utilization has been less than 25% of the bandwidth capacity</span></span>

5. <span data-ttu-id="9d11a-291">**Type de liaison** Filtrez les types de liaisons de réseau étendu suivants :</span><span class="sxs-lookup"><span data-stu-id="9d11a-291">**Link type** Filter by the following WAN links types:</span></span>

   - <span data-ttu-id="9d11a-292">Type de **site réseau**</span><span class="sxs-lookup"><span data-stu-id="9d11a-292">**Network site** type</span></span>

   - <span data-ttu-id="9d11a-293">Type **inter-sites**</span><span class="sxs-lookup"><span data-stu-id="9d11a-293">**Inter-site** type</span></span>

   - <span data-ttu-id="9d11a-294">Type **de lien entre les régions**</span><span class="sxs-lookup"><span data-stu-id="9d11a-294">**Inter-Region link** type</span></span>

6. <span data-ttu-id="9d11a-295">**Région** Filtrer par région réseau</span><span class="sxs-lookup"><span data-stu-id="9d11a-295">**Region** Filter by network region</span></span>

<span data-ttu-id="9d11a-296">Les figures suivantes présentent les filtres décrits précédemment.</span><span class="sxs-lookup"><span data-stu-id="9d11a-296">The following figures show the previously described filters.</span></span>

<span data-ttu-id="9d11a-297">Filtrez par **nom**.</span><span class="sxs-lookup"><span data-stu-id="9d11a-297">Filter by **Name**.</span></span> <span data-ttu-id="9d11a-298">Sélectionnez la liste des liens à afficher dans le graphique.</span><span class="sxs-lookup"><span data-stu-id="9d11a-298">Select the list of links that need to be displayed in the graph.</span></span>

![Filtrage par nom dans BandwidthUtilizationAnalyzer.](../media/Reskit_2012_Tools_Documentation_Image12.jpg)

<span data-ttu-id="9d11a-300">Filtre par **limite dépassée**.</span><span class="sxs-lookup"><span data-stu-id="9d11a-300">Filter by **Exceeded limit**.</span></span> <span data-ttu-id="9d11a-301">Sélectionnez **true** pour appliquer le filtre.</span><span class="sxs-lookup"><span data-stu-id="9d11a-301">Select **True** to enforce the filter.</span></span>

![Filtrage par limite dépassée.](../media/Reskit_2012_Tools_Documentation_Image13.jpg)

<span data-ttu-id="9d11a-303">Filtrer par **niveaux critiques**.</span><span class="sxs-lookup"><span data-stu-id="9d11a-303">Filter by **Critical levels**.</span></span> <span data-ttu-id="9d11a-304">Sélectionnez **true** pour appliquer le filtre.</span><span class="sxs-lookup"><span data-stu-id="9d11a-304">Select **True** to enforce the filter.</span></span>

![Filtrage par niveaux critiques.](../media/Reskit_2012_Tools_Documentation_Image14.jpg)

<span data-ttu-id="9d11a-306">Filtrer par **sous-utilisé**.</span><span class="sxs-lookup"><span data-stu-id="9d11a-306">Filter by **Under utilized**.</span></span> <span data-ttu-id="9d11a-307">Sélectionnez **true** pour appliquer le filtre.</span><span class="sxs-lookup"><span data-stu-id="9d11a-307">Select **True** to enforce the filter.</span></span>

![Filtrage par sous-utilisé.](../media/Reskit_2012_Tools_Documentation_Image15.jpg)

<span data-ttu-id="9d11a-309">Filtre par **type de lien**.</span><span class="sxs-lookup"><span data-stu-id="9d11a-309">Filter by **Link Type**.</span></span> <span data-ttu-id="9d11a-310">Sélectionnez le ou les types à afficher.</span><span class="sxs-lookup"><span data-stu-id="9d11a-310">Select the type or types that need to be displayed.</span></span>

![Filtrage par type de lien.](../media/Reskit_2012_Tools_Documentation_Image16.jpg)

<span data-ttu-id="9d11a-312">Filtrez par **région**.</span><span class="sxs-lookup"><span data-stu-id="9d11a-312">Filter by **Region**.</span></span> <span data-ttu-id="9d11a-313">Sélectionnez la liste des régions dont les liens doivent être affichés.</span><span class="sxs-lookup"><span data-stu-id="9d11a-313">Select a list of regions whose links need to be displayed.</span></span>

![Filtrage par région.](../media/Reskit_2012_Tools_Documentation_Image17.jpg)

### <a name="requirements"></a><span data-ttu-id="9d11a-315">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="9d11a-315">Requirements</span></span>

- <span data-ttu-id="9d11a-316">.NET Framework 3,5</span><span class="sxs-lookup"><span data-stu-id="9d11a-316">The .NET Framework 3.5</span></span>

- <span data-ttu-id="9d11a-317">Microsoft Excel 2010 ou Excel 2007</span><span class="sxs-lookup"><span data-stu-id="9d11a-317">Microsoft Excel 2010 or Excel 2007</span></span>

### <a name="summary"></a><span data-ttu-id="9d11a-318">Résumé</span><span class="sxs-lookup"><span data-stu-id="9d11a-318">Summary</span></span>

<span data-ttu-id="9d11a-319">L’analyseur d’utilisation de la bande passante permet de tracer l’utilisation de la bande passante audio pour le trafic UC sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="9d11a-319">Bandwidth Utilization Analyzer is used to plot the audio bandwidth utilization for UC traffic across the network.</span></span> <span data-ttu-id="9d11a-320">Cet outil peut également être utilisé pour signaler l’utilisation de la bande passante vidéo sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="9d11a-320">This tool can be used to report the utilization of video bandwidth on the network as well.</span></span>

## <a name="call-parkometer"></a><span data-ttu-id="9d11a-321">Appeler Parkometer</span><span class="sxs-lookup"><span data-stu-id="9d11a-321">Call Parkometer</span></span>
<span data-ttu-id="9d11a-322"><a name="callpark"> </a></span><span class="sxs-lookup"><span data-stu-id="9d11a-322"><a name="callpark"> </a></span></span>

<span data-ttu-id="9d11a-323">Call Parkometer est une application en ligne de commande qui fournit un accès facile à la base de données des orbites de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="9d11a-323">Call Parkometer is a command-line application that provides easy access to the Call Park orbit database.</span></span>

### <a name="description"></a><span data-ttu-id="9d11a-324">Description</span><span class="sxs-lookup"><span data-stu-id="9d11a-324">Description</span></span>

<span data-ttu-id="9d11a-325">Call Parkometer est un outil permettant de suivre les appels actuellement parqués.</span><span class="sxs-lookup"><span data-stu-id="9d11a-325">Call Parkometer is a tool to track currently parked calls.</span></span> <span data-ttu-id="9d11a-326">Il collecte également des statistiques sur les orbites et l’utilisation du serveur de parcage d’appel (CPS).</span><span class="sxs-lookup"><span data-stu-id="9d11a-326">It also collects statistics about orbits and Call Park Server (CPS) usage.</span></span> <span data-ttu-id="9d11a-327">Cet outil de ligne de commande fournit à la fois un accès en lecture et en écriture à la base de données SQL Server d’orbites CPS à partir d’un ordinateur local ou connecté à distance.</span><span class="sxs-lookup"><span data-stu-id="9d11a-327">This command-line tool provides both read and write-access to the CPS orbit SQL Server database from a local or remotely connected computer.</span></span>

<span data-ttu-id="9d11a-328">Toutes les options s’excluent mutuellement.</span><span class="sxs-lookup"><span data-stu-id="9d11a-328">All options are mutually exclusive.</span></span> <span data-ttu-id="9d11a-329">La syntaxe de la ligne de commande est la suivante :</span><span class="sxs-lookup"><span data-stu-id="9d11a-329">Command-line syntax is as follows:</span></span>

- <span data-ttu-id="9d11a-330">paramètre **-o** : répertorie toutes les plages d’orbites configurées pour ce pool.</span><span class="sxs-lookup"><span data-stu-id="9d11a-330">**-o** parameter—lists all orbit ranges configured for this pool.</span></span>

- <span data-ttu-id="9d11a-331">paramètre **-n** : répertorie toutes les orbites actuellement utilisées dans ce pool.</span><span class="sxs-lookup"><span data-stu-id="9d11a-331">**-n** parameter—lists all currently used orbits in this pool.</span></span> <span data-ttu-id="9d11a-332">Les informations affichées sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="9d11a-332">The information displayed is as follows:</span></span>

  - <span data-ttu-id="9d11a-333">URI (Uniform Resource Identifier) SIP du parqué et parqueur.</span><span class="sxs-lookup"><span data-stu-id="9d11a-333">SIP Uniform Resource Identifier (URI) of the parkee and parker.</span></span>

  - <span data-ttu-id="9d11a-334">Nom d’hôte du CPS dans lequel l’appel est parqué.</span><span class="sxs-lookup"><span data-stu-id="9d11a-334">Host name of the CPS where the call is parked.</span></span>

  - <span data-ttu-id="9d11a-335">Horodatage du moment où l’appel a été parqué.</span><span class="sxs-lookup"><span data-stu-id="9d11a-335">Time stamp of when the call was parked.</span></span>

- <span data-ttu-id="9d11a-336">paramètre **-f** — indique le nombre d’orbites libres actuellement dans le pool.</span><span class="sxs-lookup"><span data-stu-id="9d11a-336">**-f** parameter—lists the number of currently free orbits in the pool.</span></span>

- <span data-ttu-id="9d11a-337">**paramètre- \<r\> n** : répertorie \<les\> n derniers appels parqués.</span><span class="sxs-lookup"><span data-stu-id="9d11a-337">**-r \<n\>** parameter—lists the \<n\> last parked calls.</span></span> <span data-ttu-id="9d11a-338">Les informations affichées sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="9d11a-338">The information displayed is as follows:</span></span>

  - <span data-ttu-id="9d11a-339">URI SIP du parcage.</span><span class="sxs-lookup"><span data-stu-id="9d11a-339">Parkee SIP URI.</span></span>

  - <span data-ttu-id="9d11a-340">URI SIP parqueur.</span><span class="sxs-lookup"><span data-stu-id="9d11a-340">Parker SIP URI.</span></span>

  - <span data-ttu-id="9d11a-341">Nom d’hôte du CPS sur lequel l’appel a été parqué.</span><span class="sxs-lookup"><span data-stu-id="9d11a-341">Host name of the CPS where the call was parked.</span></span>

  - <span data-ttu-id="9d11a-342">Horodatage de l’extraction ou de la suppression de l’appel.</span><span class="sxs-lookup"><span data-stu-id="9d11a-342">Time stamp of when the call was retrieved or dropped.</span></span>

- <span data-ttu-id="9d11a-343">paramètre **-\<t\> n** -test de réservation d’une orbite dans la base de données pour afficher le caractère aléatoire des numéros d’orbite attribués.</span><span class="sxs-lookup"><span data-stu-id="9d11a-343">**-t\<n\>** parameter - tests reserving an orbit in the database to show the randomness of the assigned orbit numbers.</span></span>

### <a name="output"></a><span data-ttu-id="9d11a-344">Output</span><span class="sxs-lookup"><span data-stu-id="9d11a-344">Output</span></span>

<span data-ttu-id="9d11a-345">En fonction des paramètres d’entrée spécifiés à l’invite de commandes, appelez Parkometer affiche la sortie suivante :</span><span class="sxs-lookup"><span data-stu-id="9d11a-345">Depending on the input parameters that are specified at a command prompt, Call Parkometer displays the following output:</span></span>

- <span data-ttu-id="9d11a-346">Toutes les plages d’orbites configurées pour ce pool</span><span class="sxs-lookup"><span data-stu-id="9d11a-346">All orbit ranges that are configured for this pool</span></span>

- <span data-ttu-id="9d11a-347">Appels actuellement parqués</span><span class="sxs-lookup"><span data-stu-id="9d11a-347">Currently parked calls</span></span>

- <span data-ttu-id="9d11a-348">Nombre d’orbites libres (disponibles)</span><span class="sxs-lookup"><span data-stu-id="9d11a-348">Number of free (available) orbits</span></span>

- <span data-ttu-id="9d11a-349">Appels parqués récemment</span><span class="sxs-lookup"><span data-stu-id="9d11a-349">Recently parked calls</span></span>

- <span data-ttu-id="9d11a-350">Orbites réservées pour le test des valeurs d’orbite uniforme et aléatoire</span><span class="sxs-lookup"><span data-stu-id="9d11a-350">Reserved orbits for testing uniform and random orbit values</span></span>

### <a name="purpose"></a><span data-ttu-id="9d11a-351">Objectif</span><span class="sxs-lookup"><span data-stu-id="9d11a-351">Purpose</span></span>

<span data-ttu-id="9d11a-352">L’objectif de l’outil CPS est de fournir un accès à la base de données CPS à partir de la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="9d11a-352">The purpose of the CPS tool is to provide command-line access to the CPS database.</span></span> <span data-ttu-id="9d11a-353">L’administrateur peut consulter l’utilisation de CPS et déterminer le nombre d’orbites affectées à un pool.</span><span class="sxs-lookup"><span data-stu-id="9d11a-353">The administrator can view the CPS usage and determine the number of orbits assigned to a pool.</span></span>

### <a name="requirements"></a><span data-ttu-id="9d11a-354">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="9d11a-354">Requirements</span></span>

<span data-ttu-id="9d11a-355">Il n’y a aucune condition requise si cet outil est exécuté sur le même ordinateur que celui qui exécute CPS.</span><span class="sxs-lookup"><span data-stu-id="9d11a-355">There are no requirements if this tool is run on the same computer that is running CPS.</span></span> <span data-ttu-id="9d11a-356">Si cet outil est exécuté sur un ordinateur distant, la base de données SQL Server utilisée par Skype entreprise Server 2015 doit être configurée pour autoriser l’accès à distance.</span><span class="sxs-lookup"><span data-stu-id="9d11a-356">If this tool is run on a remote computer, the SQL Server database used by Skype for Business Server 2015 must be configured to allow remote access.</span></span> <span data-ttu-id="9d11a-357">Call Parkometer doit être configuré avec une chaîne de connexion de base de données SQL Server pour se connecter au serveur SQL Server du pool.</span><span class="sxs-lookup"><span data-stu-id="9d11a-357">Call Parkometer must be configured with a SQL Server database connection string to connect to the pool's SQL Server.</span></span> <span data-ttu-id="9d11a-358">Cette chaîne de connexion de base de données SQL Server est définie dans le fichier de configuration, **parkometer. exe. config**. Il doit être placé dans le même répertoire que celui où se trouve parkometer. exe.</span><span class="sxs-lookup"><span data-stu-id="9d11a-358">This SQL Server database connection string is defined in the configuration file, **parkometer.exe.config**. It must be placed in the same directory where parkometer.exe is located.</span></span> <span data-ttu-id="9d11a-359">Le fichier XML suivant est un exemple de fichier parkometer. exe. config. Les paramètres qui doivent être configurés sont le nom d’utilisateur (par exemple, mydomain\Administrator), le mot de passe (par exemple, monmotdepasse) et le nom d’hôte (par exemple, monserveur).</span><span class="sxs-lookup"><span data-stu-id="9d11a-359">The following XML file is an example of a parkometer.exe.config. The parameters that must be configured are user name (for example, mydomain\Administrator), password (for example, mypassword), and host name (for example, myserver).</span></span>

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

### <a name="examples"></a><span data-ttu-id="9d11a-360">範例</span><span class="sxs-lookup"><span data-stu-id="9d11a-360">Examples</span></span>

<span data-ttu-id="9d11a-361">Plages d’orbites déployées : le paramètre-o répertorie toutes les plages d’orbites configurées pour ce pool, comme indiqué</span><span class="sxs-lookup"><span data-stu-id="9d11a-361">Deployed orbit ranges: the -o parameter lists all orbit ranges that are configured for this pool as shown</span></span>

![Plages d’orbites dans l’appel Parkometer.](../media/Reskit_2012_Tools_Documentation_Image18.jpg)

<span data-ttu-id="9d11a-363">Appels actuellement parqués : le paramètre-n répertorie toutes les orbites actuellement utilisées sur ce pool, comme illustré ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="9d11a-363">Currently parked calls: the -n parameter lists all currently used orbits on this pool as shown</span></span>

![Appels actuellement parqués dans Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image19.jpg)

<span data-ttu-id="9d11a-365">Nombre d’orbites libres : le paramètre-f indique le nombre d’orbites libres actuellement dans le pool, comme indiqué</span><span class="sxs-lookup"><span data-stu-id="9d11a-365">Number of free orbits: the -f parameter lists the number of currently free orbits in the pool as shown</span></span>

![Orbites libres dans l’appel Parkometer.](../media/Reskit_2012_Tools_Documentation_Image20.jpg)

<span data-ttu-id="9d11a-367">Appels parqués récemment : le paramètre- \<r\> n répertorie \<les\> n derniers appels parqués, comme indiqué</span><span class="sxs-lookup"><span data-stu-id="9d11a-367">Recently parked calls: the -r \<n\> parameter lists the \<n\> last parked calls as shown</span></span>

![Appels parqués récemment dans Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image21.jpg)

<span data-ttu-id="9d11a-369">Réservation d’orbites de test : \<le\> paramètre-t n teste la réservation d’une orbite dans la base de données, comme illustré</span><span class="sxs-lookup"><span data-stu-id="9d11a-369">Test orbit reservation: the -t \<n\> parameter tests reserving an orbit in the database as shown</span></span>

![Testez les réservations d’orbites dans Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image22.jpg)

### <a name="summary"></a><span data-ttu-id="9d11a-371">Résumé</span><span class="sxs-lookup"><span data-stu-id="9d11a-371">Summary</span></span>

<span data-ttu-id="9d11a-372">Call Parkometer est un outil de ligne de commande qui fournit des informations détaillées sur le serveur de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="9d11a-372">Call Parkometer is a command-line tool that provides detailed information about the Call Park Server.</span></span>

## <a name="dbanalyze"></a><span data-ttu-id="9d11a-373">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="9d11a-373">DBAnalyze</span></span>
<span data-ttu-id="9d11a-374"><a name="dba"> </a></span><span class="sxs-lookup"><span data-stu-id="9d11a-374"><a name="dba"> </a></span></span>

### <a name="description"></a><span data-ttu-id="9d11a-375">Description</span><span class="sxs-lookup"><span data-stu-id="9d11a-375">Description</span></span>

<span data-ttu-id="9d11a-376">DBAnalyze est un outil de ligne de commande qui aide les administrateurs à rassembler des rapports d’analyse sur les bases de données Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9d11a-376">DBAnalyze is a command-line tool that helps administrators to gather analysis reports about the Skype for Business Server 2015 databases.</span></span> <span data-ttu-id="9d11a-377">DBAnalyze présente les modes suivants : diagnostic, données utilisateur, Conférence, MCU et fragmentation de disque :</span><span class="sxs-lookup"><span data-stu-id="9d11a-377">DBAnalyze has the following modes: diagnostic, user data, conference, MCUs, and disk fragmentation:</span></span>

- <span data-ttu-id="9d11a-378">**Mode diagnostic** Crée un rapport qui inclut des informations sur les tables (nombre d’enregistrements, fragmentation, taille des données et taille d’index). taille des fichiers de données et des fichiers journaux, la dernière heure de sauvegarde, répartition des contacts entre les serveurs exécutant Microsoft Office Communications Server, le nombre moyen d’autorisations, de contacts, de conteneurs, d’abonnements, de publications, de points de terminaison par utilisateur, d’utilisateurs mal hébergés, d’utilisateurs non routés, le nombre moyen de conférences organisées par utilisateur, les conférences planifiées et la version de la base de données.</span><span class="sxs-lookup"><span data-stu-id="9d11a-378">**Diagnostic mode** Creates a report that includes information about tables (number of records, fragmentation, data size, and index size), data and log file sizes, the last back-up time, contact distribution among servers that are running Microsoft Office Communications Server, the average number of permissions, contacts, containers, subscriptions, publications, endpoints per user, any improperly homed users, users that can't be routed, the average number of conferences organized per user, scheduled conferences, active conferences, and the database version.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9d11a-379">L’exécution du mode diagnostic peut affecter les performances du serveur.</span><span class="sxs-lookup"><span data-stu-id="9d11a-379">Running diagnostic mode can affect server performance.</span></span>

- <span data-ttu-id="9d11a-380">**Mode de données utilisateur** Signale les données de contact, de conteneur, d’abonnement, de publication, d’autorisation et de groupe de contacts pour un utilisateur spécifié ou pour les utilisateurs qui disposent de cet utilisateur dans leur liste de contacts et d’autorisations.</span><span class="sxs-lookup"><span data-stu-id="9d11a-380">**User data mode** Reports contact, container, subscription, publication, permission, and contact-group data for a specified user or for users who have that user in their contact and permission lists.</span></span> <span data-ttu-id="9d11a-381">Ce mode signale également les données récapitulatives des conférences auxquelles un utilisateur est organisé ou auquel il est invité.</span><span class="sxs-lookup"><span data-stu-id="9d11a-381">This mode also reports summary data for conferences that a user organizes or is invited to.</span></span>

- <span data-ttu-id="9d11a-382">**Mode conférence** Fournit des informations détaillées sur une conférence spécifique, y compris tous les détails de l’heure de planification de la Conférence, la liste des invités, la liste des types de médias autorisés pour la Conférence, les MCU actifs (unités de contrôle multipoint), la liste des participants actifs et l’état de signalisation de chaque participant.</span><span class="sxs-lookup"><span data-stu-id="9d11a-382">**Conference mode** Reports detailed data for a specific conference, including all schedule-time details for the conference, the invitee list, the list of media types allowed for the conference, active MCUs (multipoint control units), the active participant list, and each participant's signaling state.</span></span>

- <span data-ttu-id="9d11a-383">**ID de réunion de décodage** Décode un ID de réunion PSTN (réseau téléphonique commuté) spécifié par le commutateur **/pstnid** , mais ne se connecte pas au serveur principal pour obtenir des informations détaillées.</span><span class="sxs-lookup"><span data-stu-id="9d11a-383">**Decode Meeting ID** Decodes a public switched telephone network (PSTN) meeting ID that is specified by the **/pstnid** switch but does not connect to the back end for detailed information.</span></span>

- <span data-ttu-id="9d11a-384">**Résoudre la Conférence** Décode un ID de réunion PSTN spécifié par le commutateur **/pstnid** et affiche des informations sur la Conférence indiquée par l’ID.</span><span class="sxs-lookup"><span data-stu-id="9d11a-384">**Resolve conference** Decodes a PSTN meeting ID that is specified by the **/pstnid** switch and displays information about the conference indicated by the ID.</span></span>

- <span data-ttu-id="9d11a-385">**Mode MCU** Signale l’ID, le type de média, l’URL, l’état de la pulsation, la charge de conférence et la charge des participants pour chaque MCU du pool.</span><span class="sxs-lookup"><span data-stu-id="9d11a-385">**MCUs mode** Reports the ID, media type, URL, heartbeat status, conference load, and participant load for each MCU in the pool.</span></span>

- <span data-ttu-id="9d11a-386">**Mode de fragmentation de disque** Affiche l’état de fragmentation de tous les disques.</span><span class="sxs-lookup"><span data-stu-id="9d11a-386">**Disk fragmentation mode** Displays the fragmentation status of all disks.</span></span>

<span data-ttu-id="9d11a-387">Cet outil permet de diagnostiquer divers problèmes ou d’aider les administrateurs à planifier la capacité.</span><span class="sxs-lookup"><span data-stu-id="9d11a-387">This tool can be used to diagnose various problems or to assist administrators with capacity planning.</span></span> <span data-ttu-id="9d11a-388">Par exemple, si la plupart des utilisateurs hébergés sur le serveur A choisissent les utilisateurs hébergés sur le serveur B comme contacts, l’administrateur peut déplacer les utilisateurs sur le serveur A vers le serveur B afin de réduire le trafic entre les serveurs.</span><span class="sxs-lookup"><span data-stu-id="9d11a-388">For example, if most of the users homed on server A choose users homed on server B as their contacts, the administrator can move the users on server A to server B to reduce cross-server traffic.</span></span>

### <a name="output"></a><span data-ttu-id="9d11a-389">Output</span><span class="sxs-lookup"><span data-stu-id="9d11a-389">Output</span></span>

<span data-ttu-id="9d11a-390">Cet outil génère des rapports prédéfinis sur la base de données Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9d11a-390">This tool outputs predefined reports about the Skype for Business Server 2015 database.</span></span> <span data-ttu-id="9d11a-391">**Chemin d’accès**:%ProgramFiles%\Skype pour Business Server 2015 \ reskit</span><span class="sxs-lookup"><span data-stu-id="9d11a-391">**Path**: %ProgramFiles%\Skype for Business Server 2015\Reskit</span></span>

### <a name="purpose"></a><span data-ttu-id="9d11a-392">Objectif</span><span class="sxs-lookup"><span data-stu-id="9d11a-392">Purpose</span></span>

<span data-ttu-id="9d11a-393">Pour installer DbAnalyze. exe, copiez-le dans un dossier local, puis exécutez l’outil.</span><span class="sxs-lookup"><span data-stu-id="9d11a-393">To install Dbanalyze.exe, copy it to a local folder and then run the tool.</span></span> <span data-ttu-id="9d11a-394">Pour utiliser l’outil, exécutez la commande suivante à partir de la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="9d11a-394">To use the tool, run the following command from the command line.</span></span> <span data-ttu-id="9d11a-395">`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`Les descriptions des options de ligne de commande sont présentées ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="9d11a-395">`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` The descriptions for the command-line options are shown below.</span></span>

![Options de ligne de commande pour DbAnalyze. exe.](../media/Reskit_2012_Tools_Documentation_Image35.JPG)

### <a name="requirements"></a><span data-ttu-id="9d11a-397">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="9d11a-397">Requirements</span></span>

 <span data-ttu-id="9d11a-398">**Ordinateur** DBAnalyze ne peut être exécuté qu’à partir d’un ordinateur joint à un domaine sur lequel Skype entreprise Server 2015 est installé.</span><span class="sxs-lookup"><span data-stu-id="9d11a-398">**Computer** DBAnalyze can be run only from a domain-joined computer that has Skype for Business Server 2015 installed.</span></span>

 <span data-ttu-id="9d11a-399">**Réseau** L’ordinateur doit être en mesure de se connecter à la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="9d11a-399">**Network** The computer should be able to connect to the back-end database.</span></span>

 <span data-ttu-id="9d11a-400">**Logiciels** Les composants logiciels Skype entreprise Server 2015 doivent être installés avant d’exécuter DBAnalyze.</span><span class="sxs-lookup"><span data-stu-id="9d11a-400">**Software** Skype for Business Server 2015 software components must be installed before running DBAnalyze.</span></span>

 <span data-ttu-id="9d11a-401">**Les utilisateurs** Le tableau ci-dessous présente les administrateurs qui disposent des autorisations nécessaires pour accéder aux bases de données Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9d11a-401">**Users**The table below shows the administrators who have the necessary permissions to access Skype for Business Server 2015 databases.</span></span>

![Tableau des autorisations pour DbAnalyze. exe.](../media/Reskit_2012_Tools_Documentation_Image36.JPG)

> [!NOTE]
> <span data-ttu-id="9d11a-403">Un compte d’administrateur local est requis pour le mode **/Report : Disk** .</span><span class="sxs-lookup"><span data-stu-id="9d11a-403">A local administrator account is required for **/report:disk** mode.</span></span>

### <a name="examples"></a><span data-ttu-id="9d11a-404">範例</span><span class="sxs-lookup"><span data-stu-id="9d11a-404">Examples</span></span>

<span data-ttu-id="9d11a-405">Voici des exemples de commandes valides de DbAnalyze. exe :</span><span class="sxs-lookup"><span data-stu-id="9d11a-405">The following are examples of valid Dbanalyze.exe commands:</span></span>

```console
dbanalyze.exe /report:diag
dbanalyze.exe /report:user /user:usera@domainb.com
dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
dbanalyze.exe /report:resolve /pstnid:12345
dbanalyze.exe /report:mcus
dbanalyze.exe /report:disk
```

### <a name="summary"></a><span data-ttu-id="9d11a-406">Résumé</span><span class="sxs-lookup"><span data-stu-id="9d11a-406">Summary</span></span>

<span data-ttu-id="9d11a-407">DBAnalyzer permet aux administrateurs d’analyser rapidement et facilement les bases de données Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9d11a-407">DBAnalyzer provides administrators a quick and easy to analyze Skype for Business Server 2015 databases.</span></span>

## <a name="import-storage-service-data"></a><span data-ttu-id="9d11a-408">Importer les données du service de stockage</span><span class="sxs-lookup"><span data-stu-id="9d11a-408">Import Storage Service Data</span></span>
<span data-ttu-id="9d11a-409"><a name="Issd"> </a></span><span class="sxs-lookup"><span data-stu-id="9d11a-409"><a name="Issd"> </a></span></span>

<span data-ttu-id="9d11a-410">L’outil Kit de ressources ImportStorageServiceData permet de réimporter les données de point de terminaison et de file d’attente qui ont été vidées du service de stockage (LYSS) dans le service de stockage.</span><span class="sxs-lookup"><span data-stu-id="9d11a-410">The ImportStorageServiceData resource kit tool allows for re-importing Queue and Endpoint data that was flushed out of the Storage Service (LYSS) back into the Storage Service.</span></span>

### <a name="description"></a><span data-ttu-id="9d11a-411">Description</span><span class="sxs-lookup"><span data-stu-id="9d11a-411">Description</span></span>

<span data-ttu-id="9d11a-412">Les données vidées du service de stockage ont pu être automatiques (périodiques) en fonction de l’état des éléments de file d’attente ou de la taille de la base de données.</span><span class="sxs-lookup"><span data-stu-id="9d11a-412">The data flushed out of the Storage Service could have been automatic (periodic) based on Queue Item status or database size.</span></span> <span data-ttu-id="9d11a-413">Cela peut être dû à l’invocation manuelle de la cmdlet de basculement du pool ou à la cmdlet StorageServiceFullFlush (appelée par l’applet de commande de basculement du pool).</span><span class="sxs-lookup"><span data-stu-id="9d11a-413">It could have happened due to the manual invocation of the pool failover cmdlet, or the StorageServiceFullFlush cmdlet (which the pool failover cmdlet invokes).</span></span> <span data-ttu-id="9d11a-414">Notez que les données ne doivent idéalement pas être réimportées si l’une des bases de données du service de stockage (LYSS) sur les serveurs frontaux se trouve au-dessus du niveau normal, car cela entraînera probablement une plus grande exportation des données. De plus, tous les problèmes susceptibles d’avoir contribué à l’augmentation de la file d’attente du service de stockage doivent d’abord être résolus (par exemple, des erreurs de point de terminaison Exchange, des problèmes réseau ou d’autres problèmes).</span><span class="sxs-lookup"><span data-stu-id="9d11a-414">Note that data should ideally not be re-imported if any of the Storage Service (LYSS ) database size on the front ends is above the normal level, because doing so will likely just cause more data to be exported back out. Furthermore, any problems which could have contributed to errors that caused the Storage Service Queue to grow should first be resolved (for example Exchange endpoint errors, network issues, or other problems).</span></span>

 <span data-ttu-id="9d11a-415">**Scénario 1 :** lors du basculement de pool, les fichiers peuvent être vidés du service de stockage pour chaque serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="9d11a-415">**Scenario 1:** during pool failover, files may be flushed out from storage service for each front end.</span></span> <span data-ttu-id="9d11a-416">Une fois le basculement terminé, l’outil doit être exécuté pour réimporter les données.</span><span class="sxs-lookup"><span data-stu-id="9d11a-416">After failover is completed, the tool should be run to re-import the data.</span></span>

 <span data-ttu-id="9d11a-417">**Scénario 2 :** les données sont vidées automatiquement chaque jour ou en réponse à une base de données de service de stockage dépassant certains seuils de taille (par exemple 60%, 80%, 90% complet).</span><span class="sxs-lookup"><span data-stu-id="9d11a-417">**Scenario 2:** data is being flushed automatically each day or in response to Storage Service database exceeding certain size thresholds ( for example 60%, 80%, 90% full ).</span></span> <span data-ttu-id="9d11a-418">Les données vidées automatiquement doivent être régulièrement réimportées par l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="9d11a-418">This automatically flushed data should be re-imported routinely by the administrator.</span></span> <span data-ttu-id="9d11a-419">Dans la situation ci-dessus, si le Pack SCOM de surveillance n’est pas déployé, il existe des événements pour le service de stockage de Skype entreprise Server concernant les données vidées du service de stockage.</span><span class="sxs-lookup"><span data-stu-id="9d11a-419">In the above situation, if the monitoring SCOM pack is not deployed, there are events for Skype for Business Server Storage Service relating to data being flushed from the Storage Service.</span></span> <span data-ttu-id="9d11a-420">Les ID d’événement de 32075 (opération de vidage complète est démarré), 32076 (vidage complet terminé), 32082 (maintenance de niveau de maintenance démarré), 32083 (vidage du niveau de maintenance terminé), 32089 (vidage dû à la fin de la base de données).</span><span class="sxs-lookup"><span data-stu-id="9d11a-420">Event IDs of 32075 (full flush operation is started), 32076 (full flush has completed), 32082 (maintenance level flush started), 32083 (maintenance level flush complete), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="9d11a-421">Remarque ces ID d’événement correspondent à la version RTM.</span><span class="sxs-lookup"><span data-stu-id="9d11a-421">Note these event Ids correspond to the RTM release.</span></span> <span data-ttu-id="9d11a-422">Lorsqu’un administrateur voit ces événements, cela signifie qu’il existe des fichiers qui ont été vidés. Ces données doivent régulièrement être importées à l’aide de cet outil, par exemple une fois par semaine.</span><span class="sxs-lookup"><span data-stu-id="9d11a-422">When an administrator sees these events, it means that there are files that have been flushed out. This data should routinely be imported back using this tool, for example once per week.</span></span>

<span data-ttu-id="9d11a-423">Pour la version en ligne du service, si le Pack SCOM pour Skype entreprise Server est déployé, il existe de nouvelles alertes pouvant être déclenchées qui demandent à l’administrateur de réimporter les données vidées dans le service de stockage.</span><span class="sxs-lookup"><span data-stu-id="9d11a-423">For the Online Service release, if health monitoring SCOM pack for Skype for Business Server is deployed, there are new alerts which may be raised which ask the administrator to re-import the flushed data back into Storage Service.</span></span> <span data-ttu-id="9d11a-424">Il y aura un événement correspondant dans le journal des événements sur le serveur frontal qui a déclenché l’alerte.</span><span class="sxs-lookup"><span data-stu-id="9d11a-424">There will be a corresponding event in the event log on the Front End server which triggered the alert.</span></span> <span data-ttu-id="9d11a-425">L’événement fournira une description du chemin d’accès parent sous lequel se trouvent les fichiers de données vidés, ainsi que le nombre de fichiers correspondant aux critères d’alerte.</span><span class="sxs-lookup"><span data-stu-id="9d11a-425">The event will give a description of the Parent path under which the flushed data files are located, as well as how many files there are which meet the alert criteria.</span></span> <span data-ttu-id="9d11a-426">Le critère d’alerte est qu’il y a des fichiers X ou plus sous le chemin d’accès parent en particulier dont la version est d’au moins Y jours (où X et Y sont prédéfinis dans le StorageService, mais qui peuvent être remplacés en modifiant le fichier APPCONFIG.) Deux exemples d’événements pouvant déclencher l’alerte d’intégrité sont indiqués ci-dessous, la différence étant le chemin d’accès parent.</span><span class="sxs-lookup"><span data-stu-id="9d11a-426">The alert criteria is that there are X or more files under the particular parent path which are at least Y days old ( where X and Y are preset within the StorageService but can be overridden by changing the APPCONFIG file.)Two examples of events which can trigger the health alert are shown below, with the difference being their parent path.</span></span> <span data-ttu-id="9d11a-427">Une possibilité se trouve sous le partage de fichiers de service Web, tandis que l’autre peut être le répertoire de données d’application local de chaque serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="9d11a-427">One possibility is under Web service file share, while the other possibility is the local Application Data directory of each front end.</span></span> <span data-ttu-id="9d11a-428">(par exemple c:\ProgramData\Microsoft\Skype for Business Server 2015 \ StorageService).</span><span class="sxs-lookup"><span data-stu-id="9d11a-428">( for example c:\ProgramData\Microsoft\Skype for Business Server 2015\StorageService ).</span></span> <span data-ttu-id="9d11a-429">L’administrateur exécutera ensuite cet outil reskit.</span><span class="sxs-lookup"><span data-stu-id="9d11a-429">The administrator will then run this reskit tool.</span></span>

<span data-ttu-id="9d11a-430">Cet outil augmentera la charge d’UC et d’e/s sur le serveur frontal sur lequel il est exécuté, ainsi que d’autres serveurs frontaux, dans la situation où les données ne sont pas détenues par le serveur frontal sur lequel l’outil est exécuté.</span><span class="sxs-lookup"><span data-stu-id="9d11a-430">This tool will increase CPU and IO load on the front end it is running on, as well as other front ends, in the situation that the data is not owned by the front end that the tool is executed on.</span></span> <span data-ttu-id="9d11a-431">Nous vous recommandons d’exécuter cet outil lorsque les serveurs frontaux ne sont pas fortement sollicités par le processeur et la charge d’e/s, par exemple en dehors des heures de pointe.</span><span class="sxs-lookup"><span data-stu-id="9d11a-431">We recommend runng this tool when front ends are not under heavy CPU and IO load, for example outside of peak hours.</span></span> <span data-ttu-id="9d11a-432">Deuxièmement, cet outil peut 2 à 3 minutes pour importer un fichier de données.</span><span class="sxs-lookup"><span data-stu-id="9d11a-432">Secondly, this tool can 2 to 3 minutes to import one data file.</span></span> <span data-ttu-id="9d11a-433">Gardez cela à l’esprit lorsque vous évaluez la durée d’exécution de l’outil.</span><span class="sxs-lookup"><span data-stu-id="9d11a-433">Keep this in mind when estimating how long tool will be running.</span></span> <span data-ttu-id="9d11a-434">Le fichier journal détaillé généré par l’outil apparaît par défaut sur le magasin de fichiers.</span><span class="sxs-lookup"><span data-stu-id="9d11a-434">The verbose log file generated by the tool will by default appear on the File Store.</span></span> <span data-ttu-id="9d11a-435">Supprimez-le s’il n’y a aucune erreur signalée, car le fichier journal peut utiliser des dizaines de Mo ou plus.</span><span class="sxs-lookup"><span data-stu-id="9d11a-435">Delete it if there are no errors reported, because the log file can be tens of MB or more.</span></span>

![Exemples d’événements du journal des événements du serveur de stockage.](../media/Reskit_2012_Tools_Documentation_Image1.jpg)

### <a name="requirements"></a><span data-ttu-id="9d11a-437">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="9d11a-437">Requirements</span></span>

<span data-ttu-id="9d11a-438">Installez les outils du kit de ressources Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9d11a-438">Install the Skype for Business Server 2015 Resource Kit tools.</span></span> <span data-ttu-id="9d11a-439">L’outil s’exécute sur des ordinateurs liés à un domaine où Skype entreprise Server et Skype entreprise Server Management Shell sont installés.</span><span class="sxs-lookup"><span data-stu-id="9d11a-439">The tool runs on domain-joined machines where Skype for Business Server and Skype for Business Server Management Shell are installed.</span></span> <span data-ttu-id="9d11a-440">L’outil utilise une cmdlet de Management Shell pour identifier tous les serveurs frontaux du pool.</span><span class="sxs-lookup"><span data-stu-id="9d11a-440">The tool uses a cmdlet from the management shell to identify all the Front End servers in the pool.</span></span> <span data-ttu-id="9d11a-441">Deuxièmement, l’outil doit être exécuté à partir d’un ordinateur du pool sur lequel la base de données **RtcLocal** est installée.</span><span class="sxs-lookup"><span data-stu-id="9d11a-441">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="9d11a-442">Cette base de données est utilisée par l’outil pour récupérer l’emplacement du partage de fichiers WebService pour le pool.</span><span class="sxs-lookup"><span data-stu-id="9d11a-442">This database is used by the tool to retrieve the location of the WEBSERVICE file share for the pool.</span></span> <span data-ttu-id="9d11a-443">De plus, avant d’utiliser l’outil, chaque serveur frontal doit d’abord activer la communication à distance Windows PowerShell à l’aide de **Enable-PSRemoting** sur chaque serveur frontal, ainsi que la machine à partir de laquelle l’outil est exécuté.</span><span class="sxs-lookup"><span data-stu-id="9d11a-443">Additionally, before using the tool, each Front End server must first enable Windows PowerShell Remoting using **Enable-PSRemoting** on each Front End server, as well as the machine that the tool is executed from.</span></span> <span data-ttu-id="9d11a-444">Dans le cas contraire, les commandes Windows PowerShell distantes à partir de cet outil échoueront.</span><span class="sxs-lookup"><span data-stu-id="9d11a-444">Otherwise, remote Windows PowerShell commands from this tool will fail.</span></span> <span data-ttu-id="9d11a-445">La communication à distance Windows PowerShell peut être désactivée sur tous les serveurs frontaux du pool une fois terminé.</span><span class="sxs-lookup"><span data-stu-id="9d11a-445">Windows PowerShell Remoting can be turned off on all Front End servers in the pool after it is finished.</span></span> <span data-ttu-id="9d11a-446">Enfin, le compte ou les informations d’identification appelant l’outil doivent disposer d’une autorisation en lecture/écriture sur le partage de fichiers WebPart pour le pool sur lequel ils exécutent cet outil.</span><span class="sxs-lookup"><span data-stu-id="9d11a-446">Finally, the account or credential invoking the tool must have read/write permission to the webservice file share for the pool they are executing this tool on.</span></span> <span data-ttu-id="9d11a-447">Dans le cas contraire, l’outil échoue avec des erreurs d’autorisation d’e/s.</span><span class="sxs-lookup"><span data-stu-id="9d11a-447">Otherwise the tool will fail with IO Permission errors.</span></span>

> [!NOTE]
> <span data-ttu-id="9d11a-448">Sur Windows Server 2012, la communication à distance Windows PowerShell est activée par défaut, mais pas avec le système d’exploitation Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="9d11a-448">On Windows Server 2012, Windows PowerShell Remoting is enabled by default, but not on the Windows Server 2008 operating system.</span></span>

### <a name="examples"></a><span data-ttu-id="9d11a-449">範例</span><span class="sxs-lookup"><span data-stu-id="9d11a-449">Examples</span></span>

```console
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

## <a name="lcssync"></a><span data-ttu-id="9d11a-450">LCSSync</span><span class="sxs-lookup"><span data-stu-id="9d11a-450">LCSSync</span></span>
<span data-ttu-id="9d11a-451"><a name="LCSSync"> </a></span><span class="sxs-lookup"><span data-stu-id="9d11a-451"><a name="LCSSync"> </a></span></span>

<span data-ttu-id="9d11a-452">L’outil LCSSync permet de déployer le logiciel de communications Skype entreprise Server 2015 dans un environnement à forêts multiples.</span><span class="sxs-lookup"><span data-stu-id="9d11a-452">The LCSSync tool helps to deploy Skype for Business Server 2015 communications software in a multi-forest environment.</span></span> <span data-ttu-id="9d11a-453">Cet outil permet de synchroniser les utilisateurs et les groupes de différentes forêts d’utilisateurs en tant qu’objet de contact des services de domaine Active Directory avec une forêt centrale où Skype entreprise Server 2015 est installé.</span><span class="sxs-lookup"><span data-stu-id="9d11a-453">This tool is used to synchronize users and groups from different user forests as an Active Directory Domain Services contact object to a central forest where Skype for Business Server 2015 is installed.</span></span>

### <a name="description"></a><span data-ttu-id="9d11a-454">Description</span><span class="sxs-lookup"><span data-stu-id="9d11a-454">Description</span></span>

 <span data-ttu-id="9d11a-455">LCSSync utilise les objets de contact des services de domaine Active Directory synchronisés dans la forêt centrale pour activer les utilisateurs pour Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="9d11a-455">LCSSync uses the synchronized Active Directory Domain Services contact objects in the central forest to enable users for Skype for Business Server.</span></span> <span data-ttu-id="9d11a-456">Pour fournir une connexion unique, le compte d’utilisateur principal doit être mappé à l’objet de contact des services de domaine Active Directory dans la forêt centrale de Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9d11a-456">To provide single sign-in, the primary user account must be mapped to the Active Directory Domain Services contact object in the central forest for Skype for Business Server 2015.</span></span> <span data-ttu-id="9d11a-457">Cet outil permet d’effectuer ce mappage.</span><span class="sxs-lookup"><span data-stu-id="9d11a-457">This tool helps perform that mapping.</span></span> <span data-ttu-id="9d11a-458">Cet outil fournit des modèles pour la création d’agents de gestion dans le serveur Microsoft Identity Integration Server.</span><span class="sxs-lookup"><span data-stu-id="9d11a-458">This tool provides templates for creating Management Agents in the Microsoft Identity Integration Server.</span></span>

### <a name="summary"></a><span data-ttu-id="9d11a-459">Résumé</span><span class="sxs-lookup"><span data-stu-id="9d11a-459">Summary</span></span>

<span data-ttu-id="9d11a-460">L’outil LCSSync permet de déployer Skype entreprise Server 2015 dans un environnement à forêts multiples.</span><span class="sxs-lookup"><span data-stu-id="9d11a-460">The LCSSync tool helps to deploy Skype for Business Server 2015 in a multi-forest environment.</span></span>

## <a name="lookup-user-console"></a><span data-ttu-id="9d11a-461">Console utilisateur de recherche</span><span class="sxs-lookup"><span data-stu-id="9d11a-461">Lookup User Console</span></span>
<span data-ttu-id="9d11a-462"><a name="LUC"> </a></span><span class="sxs-lookup"><span data-stu-id="9d11a-462"><a name="LUC"> </a></span></span>

<span data-ttu-id="9d11a-463">L’outil LookupUserConsole affiche des informations de routage Skype entreprise Server internes sur des utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="9d11a-463">The LookupUserConsole tool displays internal Skype for Business Server routing information about specific users.</span></span> <span data-ttu-id="9d11a-464">Ces informations peuvent être utiles au support technique de Microsoft pour diagnostiquer les problèmes de déploiement et de routage.</span><span class="sxs-lookup"><span data-stu-id="9d11a-464">This information may be useful to Microsoft support personal in diagnosing deployment and routing problems.</span></span>

### <a name="description"></a><span data-ttu-id="9d11a-465">Description</span><span class="sxs-lookup"><span data-stu-id="9d11a-465">Description</span></span>

 <span data-ttu-id="9d11a-466">L’exécution de LookupUserConsole. exe ouvre une invite de commandes acceptant les adresses SIP et tente d’afficher les informations de routage Skype entreprise Server internes les concernant.</span><span class="sxs-lookup"><span data-stu-id="9d11a-466">Executing LookupUserConsole.exe will open a command prompt that accepts SIP addresses and attempts to display internal Skype for Business Server routing information relating them.</span></span> <span data-ttu-id="9d11a-467">Tapez **Exit** pour quitter l’outil LookupUserConsole.</span><span class="sxs-lookup"><span data-stu-id="9d11a-467">Type **exit** to quit the LookupUserConsole tool.</span></span>

### <a name="requirements"></a><span data-ttu-id="9d11a-468">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="9d11a-468">Requirements</span></span>

<span data-ttu-id="9d11a-469">Installez le kit de ressources Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9d11a-469">Install the Skype for Business Server 2015 Resource Kit.</span></span> <span data-ttu-id="9d11a-470">L’outil s’exécute sur les machines liées à un domaine où Skype entreprise Server est installé.</span><span class="sxs-lookup"><span data-stu-id="9d11a-470">The tool runs on domain-joined machines where Skype for Business Server is installed.</span></span>

### <a name="examples"></a><span data-ttu-id="9d11a-471">範例</span><span class="sxs-lookup"><span data-stu-id="9d11a-471">Examples</span></span>

<span data-ttu-id="9d11a-472">C:\Program Files\Skype for Business Server 2015 \ reskit\>LookupUserConsole. exe</span><span class="sxs-lookup"><span data-stu-id="9d11a-472">C:\Program Files\Skype for Business Server 2015\ResKit\>LookupUserConsole.exe</span></span>

```console
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

## <a name="msturnping"></a><span data-ttu-id="9d11a-473">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="9d11a-473">MsTurnPing</span></span>
<span data-ttu-id="9d11a-474"><a name="MsTurnPing"> </a></span><span class="sxs-lookup"><span data-stu-id="9d11a-474"><a name="MsTurnPing"> </a></span></span>

<span data-ttu-id="9d11a-475">L’outil MSTurnPing permet à un administrateur du logiciel de communications Skype entreprise Server 2015 de vérifier l’état des serveurs exécutant les services d’authentification audio/vidéo et audio/vidéo, ainsi que les serveurs qui exécutent les services de stratégie de bande passante dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="9d11a-475">The MSTurnPing tool allows an administrator of Skype for Business Server 2015 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

### <a name="description"></a><span data-ttu-id="9d11a-476">Description</span><span class="sxs-lookup"><span data-stu-id="9d11a-476">Description</span></span>

<span data-ttu-id="9d11a-477">L’outil MSTurnPing permet à un administrateur du logiciel de communications Skype entreprise Server 2015 de vérifier l’état des serveurs exécutant les services d’authentification audio/vidéo et audio/vidéo, ainsi que les serveurs qui exécutent les services de stratégie de bande passante dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="9d11a-477">The MSTurnPing tool allows an administrator of Skype for Business Server 2015 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

<span data-ttu-id="9d11a-478">L’outil permet à l’administrateur d’effectuer les tests suivants :</span><span class="sxs-lookup"><span data-stu-id="9d11a-478">The tool allows the administrator to perform the following tests:</span></span>

1. <span data-ttu-id="9d11a-479">Test du serveur Edge a/V : l’outil effectue des tests sur tous les serveurs Edge A/V de la topologie en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="9d11a-479">A/V Edge Server test: The tool performs tests against all A/V Edge Servers in the topology by doing the following:</span></span>

   - <span data-ttu-id="9d11a-480">Vérifier que le service d’authentification audio/vidéo Skype entreprise Server est démarré et peut émettre des informations d’identification correctes.</span><span class="sxs-lookup"><span data-stu-id="9d11a-480">Verifying that the Skype for Business Server Audio/Video Authentication service is started and can issue proper credentials.</span></span>

   - <span data-ttu-id="9d11a-481">Vérification que le service Edge audio/vidéo de Skype entreprise Server est démarré et peut allouer correctement les ressources sur le serveur Edge externe.</span><span class="sxs-lookup"><span data-stu-id="9d11a-481">Verifying that the Skype for Business Server Audio/Video Edge service is started and can allocate the resources on the external edge successfully.</span></span>

2. <span data-ttu-id="9d11a-482">Test du service de stratégie de bande passante : l’outil effectue des tests sur tous les serveurs qui exécutent les services de stratégie de bande passante dans la topologie en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="9d11a-482">Bandwidth Policy Service test: The tool performs tests against all the servers that are running the Bandwidth Policy Services in the topology by doing the following:</span></span>

   - <span data-ttu-id="9d11a-483">Vérifier que le service de stratégie de bande passante de Skype entreprise Server (authentification) est démarré et peut émettre des informations d’identification appropriées.</span><span class="sxs-lookup"><span data-stu-id="9d11a-483">Verifying that the Skype for Business Server Bandwidth Policy Service (Authentication) is started and can issue proper credentials.</span></span>

   - <span data-ttu-id="9d11a-484">Vérification que le service de stratégie de bande passante (Core) Skype entreprise Server est démarré et peut effectuer la vérification de la bande passante.</span><span class="sxs-lookup"><span data-stu-id="9d11a-484">Verifying that the Skype for Business Server Bandwidth Policy Service (Core) is started and can perform the bandwidth check successfully.</span></span>

<span data-ttu-id="9d11a-485">Cet outil doit être exécuté à partir d’un ordinateur qui fait partie de la topologie et sur lequel le magasin local est installé.</span><span class="sxs-lookup"><span data-stu-id="9d11a-485">This tool must be run from a computer that is part of the topology and has the local store installed.</span></span>

### <a name="output"></a><span data-ttu-id="9d11a-486">Output</span><span class="sxs-lookup"><span data-stu-id="9d11a-486">Output</span></span>

<span data-ttu-id="9d11a-487">L’outil renvoie les résultats de chacune des opérations.</span><span class="sxs-lookup"><span data-stu-id="9d11a-487">The tool outputs the results of each of the operations.</span></span>

- <span data-ttu-id="9d11a-488">Si le test **AudioVideoEdgeServer** est effectué, les sorties de l’outil sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="9d11a-488">If the **AudioVideoEdgeServer** test is performed, the tool outputs are the following:</span></span>

  - <span data-ttu-id="9d11a-489">Les résultats des tests des ordinateurs qui fournissent le service d’authentification audio/vidéo Skype entreprise Server 2015 dans la topologie</span><span class="sxs-lookup"><span data-stu-id="9d11a-489">The test results of the computers that provide the Skype for Business Server 2015 Audio/Video Authentication service in the topology</span></span>

  - <span data-ttu-id="9d11a-490">Les résultats des tests des ordinateurs qui fournissent le service Edge audio/vidéo de Skype entreprise Server 2015 dans la topologie</span><span class="sxs-lookup"><span data-stu-id="9d11a-490">The test results of the computers that provide the Skype for Business Server 2015 Audio/Video Edge service in the topology</span></span>

- <span data-ttu-id="9d11a-491">Si le test **BandwidthPolicyServer** est effectué, les sorties de l’outil sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="9d11a-491">If the **BandwidthPolicyServer** test is performed, the tool outputs are the following:</span></span>

  - <span data-ttu-id="9d11a-492">Les résultats des tests des ordinateurs qui fournissent le service de stratégie de bande passante de Skype entreprise Server 2015 (authentification) dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="9d11a-492">The test results of the computers that provide the Skype for Business Server 2015 Bandwidth Policy Service (Authentication) in the topology</span></span>

  - <span data-ttu-id="9d11a-493">Les résultats des tests des ordinateurs qui fournissent le service de stratégie de bande passante (Core) de Skype entreprise Server 2015 dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="9d11a-493">The test results of the computers that provide the Skype for Business Server 2015 Bandwidth Policy Service (Core) in the topology</span></span>

### <a name="requirements"></a><span data-ttu-id="9d11a-494">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="9d11a-494">Requirements</span></span>

- <span data-ttu-id="9d11a-495">Cet outil doit être exécuté à partir d’un ordinateur qui se trouve dans la topologie et qui a le magasin local.</span><span class="sxs-lookup"><span data-stu-id="9d11a-495">This tool must be run from a computer that is in the topology and that has the local store.</span></span>

- <span data-ttu-id="9d11a-496">L’outil doit être exécuté en tant qu’administrateur ayant accès au magasin local.</span><span class="sxs-lookup"><span data-stu-id="9d11a-496">The tool must be run as an administrator who has access to the local store.</span></span>

### <a name="examples"></a><span data-ttu-id="9d11a-497">範例</span><span class="sxs-lookup"><span data-stu-id="9d11a-497">Examples</span></span>

<span data-ttu-id="9d11a-498">Voici un exemple de l’entrée d’outil.</span><span class="sxs-lookup"><span data-stu-id="9d11a-498">The following is an example of the tool input.</span></span>

```console
MsTurnPing -ServerRole AudioVideoEdgeServer

MsTurnPing -ServerRole BandwidthPolicyServer
```

### <a name="summary"></a><span data-ttu-id="9d11a-499">Résumé</span><span class="sxs-lookup"><span data-stu-id="9d11a-499">Summary</span></span>

<span data-ttu-id="9d11a-500">Cet outil peut être une ressource précieuse pour les administrateurs de Skype entreprise Server 2015 qui souhaitent vérifier l’état des serveurs qui exécutent les services de stratégie de bande passante et audio/vidéo.</span><span class="sxs-lookup"><span data-stu-id="9d11a-500">This tool can be a valuable resource to Skype for Business Server 2015 administrators who want to check the status of the servers that are running audio/video and bandwidth policy services.</span></span>

## <a name="network-configuration-viewer"></a><span data-ttu-id="9d11a-501">Afficheur de configuration réseau</span><span class="sxs-lookup"><span data-stu-id="9d11a-501">Network Configuration Viewer</span></span>
<span data-ttu-id="9d11a-502"><a name="NCV"> </a></span><span class="sxs-lookup"><span data-stu-id="9d11a-502"><a name="NCV"> </a></span></span>

<span data-ttu-id="9d11a-503">La visionneuse de configuration réseau peut être utilisée par les administrateurs logiciels de communications de Skype entreprise Server 2015 pour afficher la topologie de réseau de contrôle d’admission des appels (CAC) pour une entreprise qui est configurée pour autoriser les sessions de communication en temps réel, telles que appels vocaux ou vidéo en fonction de la capacité de bande passante spécifiée.</span><span class="sxs-lookup"><span data-stu-id="9d11a-503">Network Configuration Viewer can be used by Skype for Business Server 2015 communications software administrators to view call admission control (CAC) network topology for an enterprise that is provisioned to allow real-time communication sessions, such as voice or video calls based on specified bandwidth capacity.</span></span> <span data-ttu-id="9d11a-504">Les administrateurs de Skype entreprise Server 2015 définissent les stratégies de contrôle d’admission des appels, qui sont appliquées par les services de stratégie de bande passante installés avec Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9d11a-504">Skype for Business Server 2015 administrators define CAC policies, which are enforced by the Bandwidth Policy services that are installed with Skype for Business Server 2015.</span></span>

### <a name="description"></a><span data-ttu-id="9d11a-505">Description</span><span class="sxs-lookup"><span data-stu-id="9d11a-505">Description</span></span>

<span data-ttu-id="9d11a-506">La visionneuse de configuration réseau (NetworkConfigurationViewer. exe) permet aux administrateurs d’effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="9d11a-506">Network Configuration Viewer (NetworkConfigurationViewer.exe) allows administrators to perform the following tasks:</span></span>

- <span data-ttu-id="9d11a-507">Chargez et affichez la topologie de réseau CAC à partir d’un déploiement de Skype entreprise Server 2015 dans un format graphique.</span><span class="sxs-lookup"><span data-stu-id="9d11a-507">Load and view CAC network topology from a Skype for Business Server 2015 deployment in a graphical format.</span></span>

- <span data-ttu-id="9d11a-508">Chargez et affichez la topologie de réseau CAC à partir d’un fichier journal de serveur de stratégie de bande passante dans un format graphique.</span><span class="sxs-lookup"><span data-stu-id="9d11a-508">Load and view CAC network topology from a Bandwidth Policy Server log file in a graphical format.</span></span>

- <span data-ttu-id="9d11a-509">Enregistrez et stockez la topologie de réseau CAC au format XML sur le disque.</span><span class="sxs-lookup"><span data-stu-id="9d11a-509">Save and store CAC network topology in an XML format on the disk.</span></span>

- <span data-ttu-id="9d11a-510">Enregistrer et stocker le diagramme de topologie réseau CAC au format JPG ou BMP.</span><span class="sxs-lookup"><span data-stu-id="9d11a-510">Save and store CAC network topology diagram in JPG or BMP format.</span></span>

- <span data-ttu-id="9d11a-511">Afficher les données de configuration de la topologie réseau CAC.</span><span class="sxs-lookup"><span data-stu-id="9d11a-511">View CAC network topology configuration data.</span></span>

- <span data-ttu-id="9d11a-512">Afficher la topologie du réseau CAC sous la forme d’un style d’affichage arborescent.</span><span class="sxs-lookup"><span data-stu-id="9d11a-512">View CAC network topology in a tree-view style.</span></span>

- <span data-ttu-id="9d11a-513">Définissez des connecteurs personnalisés pour les liens de topologie de réseau CAC (par exemple, liaisons de site à région, de région à région et de site à site).</span><span class="sxs-lookup"><span data-stu-id="9d11a-513">Define custom connectors for CAC network topology links (for example, site-to-region, region-to-region, and site-to-site links).</span></span>

- <span data-ttu-id="9d11a-514">Afficher les informations de site, les informations de région et les stratégies de bande passante et les liaisons réseau configurées pour la topologie du réseau CAC.</span><span class="sxs-lookup"><span data-stu-id="9d11a-514">View CAC network topology site information, region Information, and provisioned bandwidth policies and network links.</span></span>

### <a name="purpose"></a><span data-ttu-id="9d11a-515">Objectif</span><span class="sxs-lookup"><span data-stu-id="9d11a-515">Purpose</span></span>

<span data-ttu-id="9d11a-516">Afficher les liens de topologie du réseau CAC d’entreprise dans une interface graphique.</span><span class="sxs-lookup"><span data-stu-id="9d11a-516">View enterprise CAC network topology links in a graphical interface.</span></span>

### <a name="examples"></a><span data-ttu-id="9d11a-517">範例</span><span class="sxs-lookup"><span data-stu-id="9d11a-517">Examples</span></span>

 <span data-ttu-id="9d11a-518">**Chargez et affichez la topologie réseau CAC à partir d’un déploiement Skype entreprise server 2015 au format graphique**: les administrateurs de Skype entreprise Server 2015 peuvent charger et afficher la configuration de la topologie du réseau CAC sur n’importe quel ordinateur Skype entreprise Server 2015 en utilisant l’option **Télécharger la configuration réseau** , comme illustré dans la figure ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="9d11a-518">**Load and view CAC network topology from a Skype for Business Server 2015 deployment in a graphical format**: Skype for Business Server 2015 administrators can load and view CAC network topology configuration on any Skype for Business Server 2015 computer by using the **Download Network Configuration** option as shown in the figure below.</span></span> <span data-ttu-id="9d11a-519">L’outil ne parviendra pas à télécharger ou à afficher une configuration de ce type lorsqu’il est déployé sur un ordinateur qui n’a pas de connectivité au magasin de configurations Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9d11a-519">The tool will fail to download or view such a configuration when deployed on a computer that does not have connectivity to the Skype for Business Server 2015 configuration store.</span></span>

![Téléchargement de la configuration réseau.](../media/Reskit_2012_Tools_Documentation_Image23.jpg)

 <span data-ttu-id="9d11a-521">**Chargez et affichez la topologie de réseau CAC à partir d’un fichier journal de serveur de stratégie de bande passante dans un format graphique :** Les serveurs de stratégie de bande passante de Skype entreprise Server 2015 enregistrent la topologie de réseau CAC dans le cadre du mécanisme de journalisation sous l’emplacement de partage de fichiers de Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9d11a-521">**Load and View CAC network topology from a Bandwidth Policy server log file in a graphical format:** Skype for Business Server 2015 Bandwidth Policy servers save the CAC network topology as a part of the logging mechanism under the Skype for Business Server 2015 file share location.</span></span> <span data-ttu-id="9d11a-522">Les administrateurs de Skype entreprise Server 2015 peuvent afficher ce type de fichier dans un format graphique à l’aide de l’option **ouvrir la configuration du réseau** , comme indiqué ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="9d11a-522">Skype for Business Server 2015 administrators can view such a file in a graphical format by using the **Open Network Configuration** option as shown below.</span></span>

![Ouverture d’un fichier journal du serveur de stratégie de bande passante.](../media/Reskit_2012_Tools_Documentation_Image24.jpg)

<span data-ttu-id="9d11a-524">Enregistrer et stocker la topologie de réseau CAC au format XML sur le disque : les administrateurs de Skype entreprise Server 2015 peuvent enregistrer le fichier de configuration de la topologie réseau CAC au format XML à l’aide de l’option **enregistrer une copie de la configuration réseau** , comme indiqué ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="9d11a-524">Save and store CAC network topology in an XML format on the disk: Skype for Business Server 2015 administrators can save the CAC network topology configuration file in an XML format by using the **Save a copy of Network Configuration** option as shown below.</span></span> <span data-ttu-id="9d11a-525">Le fichier de configuration enregistré peut ensuite être utilisé hors connexion à des fins d’affichage graphique.</span><span class="sxs-lookup"><span data-stu-id="9d11a-525">The saved configuration file can then be used offline for graphical viewing purposes.</span></span>

![Enregistrement de la configuration réseau sous forme de fichier XML.](../media/Reskit_2012_Tools_Documentation_Image25.jpg)

<span data-ttu-id="9d11a-527">Enregistrer et stocker le diagramme de la topologie réseau CAC au format JPG ou BMP : les administrateurs de Skype entreprise Server 2015 peuvent enregistrer la configuration de la topologie du réseau CAC dans un format graphique (formats de fichiers JPG et BMP) à l’aide de l’option **enregistrer le diagramme de configuration réseau en tant qu’image** , comme illustré ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="9d11a-527">Save and Store CAC network topology diagram in JPG or BMP format: Skype for Business Server 2015 administrators can save the CAC network topology configuration in a graphical format (JPG and BMP file formats) by using the **Save Network Configuration diagram as picture** option as shown below.</span></span>

![Enregistrement de la configuration réseau en tant qu’image.](../media/Reskit_2012_Tools_Documentation_Image26.jpg)

 <span data-ttu-id="9d11a-529"><strong>Afficher les données de configuration de la topologie réseau CAC :</strong> Les administrateurs de Skype entreprise Server 2015 peuvent afficher des données de configuration réseau, telles que des régions réseau, des sites réseau, des profils de bande passante et des adresses IP de sous-réseau de site dans un format texte à l’aide de l’option Afficher les données de configuration réseau, comme indiqué ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="9d11a-529"><strong>View CAC network topology configuration data:</strong>Skype for Business Server 2015 administrators can view related network configuration data such as network regions, network sites, bandwidth profiles, and site subnet IP addresses in a textual format by using the View Network Configuration data option as shown below.</span></span>

![Affichage des données de configuration réseau.](../media/Reskit_2012_Tools_Documentation_Image27.jpg)

 <span data-ttu-id="9d11a-531">**Afficher la topologie du réseau CAC sous forme d’arborescence :** Les administrateurs de Skype entreprise Server 2015 peuvent afficher les données de configuration du réseau associées dans un style d’affichage de l’arborescence graphique à l’aide du panneau de configuration sur le côté gauche de la fenêtre outil, comme illustré ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="9d11a-531">**View CAC network topology in a tree-view style:** Skype for Business Server 2015 administrators can view related network configuration data in a graphical tree view style by using the control panel on the left side of the tool window as shown below.</span></span>

![Affichage des données de configuration réseau dans une arborescence.](../media/Reskit_2012_Tools_Documentation_Image28.jpg)

 <span data-ttu-id="9d11a-533">**Définissez des connecteurs personnalisés pour les liens de topologie de réseau CAC (tels que les liens de site à région, région à région et de site à site) :** Les administrateurs de Skype entreprise Server 2015 peuvent définir des connecteurs graphiques personnalisés pour la configuration du réseau CAC WAN Links à l’aide de l’option paramètres, comme illustré ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="9d11a-533">**Define custom connectors for CAC network topology links (such as site-to-region, region-to-region, and site-to-site links):** Skype for Business Server 2015 administrators can define custom graphical connectors for CAC network configuration WAN links by using the Settings option as shown below.</span></span> <span data-ttu-id="9d11a-534">Cela permet de différencier les différents types de liaisons réseau configurées dans la configuration réseau.</span><span class="sxs-lookup"><span data-stu-id="9d11a-534">This helps differentiate between various types of network links that are provisioned in the network configuration.</span></span>

![Outils](../media/Reskit_2012_Tools_Documentation_Image29.jpg)

 <span data-ttu-id="9d11a-536">**Afficher les informations de site, les informations de région et les stratégies de bande passante de mise en service de la topologie réseau CAC :** Les administrateurs de Skype entreprise Server 2015 peuvent afficher les informations relatives à la région réseau CAC, les informations de site et les informations de mise en service de la bande passante CAC à l’aide des options indiquées ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="9d11a-536">**View CAC network topology site information, region information, and provisioned bandwidth policies:** Skype for Business Server 2015 administrators can view related CAC network region information, site information, and CAC bandwidth provisioning information by using options shown below.</span></span> <span data-ttu-id="9d11a-537">(Par exemple, cliquez sur **info** dans une région réseau ou un objet de site réseau.)</span><span class="sxs-lookup"><span data-stu-id="9d11a-537">(For example, click **Info** in a network region or network site object.)</span></span>

![Définition de connecteurs personnalisés pour votre réseau.](../media/Reskit_2012_Tools_Documentation_Image30.jpg)

### <a name="summary"></a><span data-ttu-id="9d11a-539">Résumé</span><span class="sxs-lookup"><span data-stu-id="9d11a-539">Summary</span></span>

<span data-ttu-id="9d11a-540">Cet outil peut être une ressource précieuse pour les administrateurs de Skype entreprise Server 2015 qui souhaitent afficher la topologie de réseau CAC pour leur déploiement dans un format graphique.</span><span class="sxs-lookup"><span data-stu-id="9d11a-540">This tool can be a valuable resource to Skype for Business Server 2015 administrators who would like to view CAC network topology for their deployment in a graphical format.</span></span>

## <a name="response-group-agent-live"></a><span data-ttu-id="9d11a-541">Response Group agent Live</span><span class="sxs-lookup"><span data-stu-id="9d11a-541">Response Group Agent Live</span></span>
<span data-ttu-id="9d11a-542"><a name="RGAL"> </a></span><span class="sxs-lookup"><span data-stu-id="9d11a-542"><a name="RGAL"> </a></span></span>

<span data-ttu-id="9d11a-543">L’application Response Group offre aux agents la possibilité d’accéder à des informations en temps réel utiles à l’aide de son service Web intégré.</span><span class="sxs-lookup"><span data-stu-id="9d11a-543">The Response Group application gives agents the ability to access useful real-time information using its built-in Web service.</span></span> <span data-ttu-id="9d11a-544">Malheureusement, aucune vue graphique de ces données n’est disponible en dehors de l’application.</span><span class="sxs-lookup"><span data-stu-id="9d11a-544">Unfortunately, no graphical view of this data is available outside the application.</span></span> <span data-ttu-id="9d11a-545">L’outil Response Group agent Live Resource Kit résout ce problème en fournissant un moyen simple et graphique d’accéder à ces informations, améliorés par des informations logicielles de communication Skype entreprise en temps réel, telles que la présence d’autres agents.</span><span class="sxs-lookup"><span data-stu-id="9d11a-545">The Response Group Agent Live Resource Kit tool solves this issue by providing a simple and graphical way to access this information, enhanced with real-time Skype for Business communications software information such as the presence of other agents.</span></span>

### <a name="description"></a><span data-ttu-id="9d11a-546">Description</span><span class="sxs-lookup"><span data-stu-id="9d11a-546">Description</span></span>

<span data-ttu-id="9d11a-547">Response Group agent Live est une application Windows qui fournit des fonctionnalités de connexion et de déconnexion, ainsi que des informations en temps réel (telles que l’appartenance à un groupe et le nombre actuel d’appels) aux agents Response Group.</span><span class="sxs-lookup"><span data-stu-id="9d11a-547">Response Group Agent Live is a Windows application that provides sign-in and sign-out functionality and some real-time information (such as group membership and current number of calls) to Response Group agents.</span></span> <span data-ttu-id="9d11a-548">Il s’agit d’une version améliorée de la page groupes d’agents (accessible à partir de Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="9d11a-548">It is meant to be an enhanced version of the Agent Groups page (accessible from Skype for Business.</span></span>

### <a name="purpose"></a><span data-ttu-id="9d11a-549">Objectif</span><span class="sxs-lookup"><span data-stu-id="9d11a-549">Purpose</span></span>

<span data-ttu-id="9d11a-550">L’application Response Group place en file d’attente les appels entrants, puis les achemine vers les groupes d’agents.</span><span class="sxs-lookup"><span data-stu-id="9d11a-550">The Response Group application queues incoming calls, and then routes them to agent groups.</span></span> <span data-ttu-id="9d11a-551">Pour prendre des décisions éclairées concernant les appels à traiter, les agents peuvent accéder aux informations en temps réel sur leurs groupes d’agents, telles que les autres agents disponibles et le nombre d’appels en attente dans chaque file d’attente.</span><span class="sxs-lookup"><span data-stu-id="9d11a-551">To make informed decisions about which calls to service, agents can access real-time information about their agent groups, such as what other agents are available and how many calls are waiting in each queue.</span></span> <span data-ttu-id="9d11a-552">Ces informations, initialement accessibles uniquement par le biais du service Response Group, sont mises à disposition de manière intuitive par Response Group agent Live.</span><span class="sxs-lookup"><span data-stu-id="9d11a-552">This information, initially accessible only through the Response Group service, is made available in an intuitive way by Response Group Agent Live.</span></span>

#### <a name="features"></a><span data-ttu-id="9d11a-553">Fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="9d11a-553">Features</span></span>

<span data-ttu-id="9d11a-554">L’outil Response Group agent Live est basé sur le service Response Group et le kit de développement logiciel (SDK) Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9d11a-554">The Response Group Agent Live tool is built on the Response Group service and the Skype for Business Server 2015 SDK.</span></span> <span data-ttu-id="9d11a-555">Il fournit aux agents Response Group les informations et les fonctionnalités disponibles auprès du service Response Group (par exemple, l’appartenance à un groupe, la présence d’autres agents et le nombre d’appels en attente).</span><span class="sxs-lookup"><span data-stu-id="9d11a-555">It provides Response Group agents the information and capabilities that are available from the Response Group service (such as group membership, presence of other agents, and number of waiting calls).</span></span>

<span data-ttu-id="9d11a-556">La figure ci-dessous illustre l’interface principale de Response Group agent Live.</span><span class="sxs-lookup"><span data-stu-id="9d11a-556">The figure below illustrates the main interface of Response Group Agent Live.</span></span>

![Outil Response Group agent Live.](../media/Reskit_2012_Tools_Documentation_Image37.JPG)

<span data-ttu-id="9d11a-558">Les trois fonctionnalités principales suivantes sont disponibles pour les agents dans Response Group agent Live :</span><span class="sxs-lookup"><span data-stu-id="9d11a-558">The following three main features are available for agents in Response Group Agent Live:</span></span>

- <span data-ttu-id="9d11a-559">**Connexion/déconnexion :** Contrairement à la page des groupes d’agents (accessible à partir de Skype entreprise Server 2015), Response Group agent Live autorise uniquement les agents à se connecter ou à déconnecter tous les groupes d’agents en même temps.</span><span class="sxs-lookup"><span data-stu-id="9d11a-559">**Sign-in/out:** Contrary to the Agent Groups page (accessible from Skype for Business Server 2015), Response Group Agent Live allows only agents to sign-in or out of all agent groups at once.</span></span> <span data-ttu-id="9d11a-560">Cette application propose trois méthodes rapides pour la connexion et la déconnexion des agents :</span><span class="sxs-lookup"><span data-stu-id="9d11a-560">This application provides three quick ways for agents to sign in or out:</span></span>

  - <span data-ttu-id="9d11a-561">Cliquez sur le bouton se connecter/déconnecter (vert et rouge) dans l’application.</span><span class="sxs-lookup"><span data-stu-id="9d11a-561">Click the Sign-in/out (green and red) buttons within the application.</span></span>

  - <span data-ttu-id="9d11a-562">Cliquez avec le bouton droit sur l’icône de la barre d’état système, puis sélectionnez se connecter ou se déconnecter.</span><span class="sxs-lookup"><span data-stu-id="9d11a-562">Right-click the system tray icon, and select sign in or sign out.</span></span>

  - <span data-ttu-id="9d11a-563">Utilisation de raccourcis clavier configurables.</span><span class="sxs-lookup"><span data-stu-id="9d11a-563">Using configurable keyboard shortcuts.</span></span>

- <span data-ttu-id="9d11a-564">**Appartenance au groupe :** Lorsqu’un groupe d’agents est sélectionné, Response Group agent Live affiche la liste des agents de ce groupe dans le volet de droite.</span><span class="sxs-lookup"><span data-stu-id="9d11a-564">**Group membership:** When an agent group is selected, Response Group Agent Live displays the list of agents in this group in the right pane.</span></span> <span data-ttu-id="9d11a-565">Si Skype entreprise Server 2015 s’exécute sur le même ordinateur que cette application, les informations de présence et la carte de visite s’affichent dans l’agent Response Group agent Live.</span><span class="sxs-lookup"><span data-stu-id="9d11a-565">If Skype for Business Server 2015 is running on the same computer as this application, presence information and the contact card are displayed in the Response Group Agent Live.</span></span> <span data-ttu-id="9d11a-566">Les agents peuvent envoyer un message instantané ou appeler d’autres agents directement à partir de là.</span><span class="sxs-lookup"><span data-stu-id="9d11a-566">Agents can send an IM or call other agents directly from there.</span></span>

- <span data-ttu-id="9d11a-567">**Statistiques en temps réel :** Response Group agent Live fournit des statistiques en temps réel pour tous les groupes d’agents.</span><span class="sxs-lookup"><span data-stu-id="9d11a-567">**Real-time statistics:** Response Group Agent Live provides real-time statistics for all agent groups.</span></span> <span data-ttu-id="9d11a-568">La fréquence de mise à jour est d’une minute.</span><span class="sxs-lookup"><span data-stu-id="9d11a-568">The update frequency is one minute.</span></span> <span data-ttu-id="9d11a-569">Lorsqu’un groupe Response Group répond à un appel, un indicateur visuel est ajouté en regard du nom du groupe avec le nombre actuel d’appels en file d’attente.</span><span class="sxs-lookup"><span data-stu-id="9d11a-569">When a call is answered by a Response Group, a visual indicator is added next to the group name with the current number of queued calls.</span></span> <span data-ttu-id="9d11a-570">La suspension du pointeur sur un groupe affiche également le temps d’attente le plus long.</span><span class="sxs-lookup"><span data-stu-id="9d11a-570">Pausing the pointer over a group also displays the longest waiting time.</span></span>

### <a name="requirements"></a><span data-ttu-id="9d11a-571">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="9d11a-571">Requirements</span></span>

<span data-ttu-id="9d11a-572">Response Group agent Live requiert .NET Framework 4,0.</span><span class="sxs-lookup"><span data-stu-id="9d11a-572">Response Group Agent Live requires the .NET Framework 4.0.</span></span> <span data-ttu-id="9d11a-573">De plus, pour tirer parti des fonctionnalités de présence et de carte de visite, Skype entreprise doit être installé localement (et être en cours d’exécution).</span><span class="sxs-lookup"><span data-stu-id="9d11a-573">In addition, to take advantage of the presence and contact card features, Skype for Business must be installed locally (and be running).</span></span>

#### <a name="configuration"></a><span data-ttu-id="9d11a-574">Configuration</span><span class="sxs-lookup"><span data-stu-id="9d11a-574">Configuration</span></span>

<span data-ttu-id="9d11a-575">Response Group agent Live peut être personnalisé en fonction des préférences individuelles à l’aide de la boîte de dialogue Options de l’application.</span><span class="sxs-lookup"><span data-stu-id="9d11a-575">Response Group Agent Live can be customized to individual preferences by using the Options dialog box in the application.</span></span> <span data-ttu-id="9d11a-576">En outre, l’administrateur peut définir l’adresse hôte par défaut en modifiant directement la propriété defaultHostAddress du fichier RGAgentLive. exe. config.</span><span class="sxs-lookup"><span data-stu-id="9d11a-576">In addition, the administrator can define the default host address by editing directly the defaultHostAddress property of the RGAgentLive.exe.config file.</span></span>

<span data-ttu-id="9d11a-577">La figure ci-dessous illustre la boîte de dialogue Options que les agents peuvent utiliser pour configurer l’adresse hôte et les touches de raccourci.</span><span class="sxs-lookup"><span data-stu-id="9d11a-577">The figure below illustrates the Options dialog box that agents can use to configure the host address and shortcut keys.</span></span> <span data-ttu-id="9d11a-578">Pour accéder à cette boîte de dialogue, cliquez sur le bouton options en haut à droite de l’interface principale.</span><span class="sxs-lookup"><span data-stu-id="9d11a-578">This dialog is accessed by clicking the Options button on the top right of the main interface.</span></span>

![Boîte de dialogue Options de l’agent Response Group.](../media/Reskit_2012_Tools_Documentation_Image38.JPG)

<span data-ttu-id="9d11a-580">Les trois paramètres suivants peuvent être personnalisés dans la configuration de Response Group agent Live :</span><span class="sxs-lookup"><span data-stu-id="9d11a-580">The following three different settings can be customized in the Response Group Agent Live configuration:</span></span>

- <span data-ttu-id="9d11a-581">Adresse de l’hôte : il s’agit généralement du nom de domaine complet du pool de l’agent.</span><span class="sxs-lookup"><span data-stu-id="9d11a-581">Host address: This is typically the web pool FQDN belonging to the agent's home pool.</span></span> <span data-ttu-id="9d11a-582">L’adresse exacte du service Response Group est automatiquement dérivée en arrière-plan à partir de ces informations (en ajoutant le chemin d’accès approprié après l’hôte).</span><span class="sxs-lookup"><span data-stu-id="9d11a-582">The exact Response Group service address is automatically derived in the background from this information (by appending the right path after the host).</span></span>

- <span data-ttu-id="9d11a-583">Raccourcis : les raccourcis exacts de connexion/déconnexion peuvent être personnalisés.</span><span class="sxs-lookup"><span data-stu-id="9d11a-583">Shortcuts: The exact shortcuts to sign-in/out can be customized.</span></span> <span data-ttu-id="9d11a-584">La seule limitation est que les deux raccourcis doivent contenir la clé « Windows logo » (en plus d’au moins une autre clé).</span><span class="sxs-lookup"><span data-stu-id="9d11a-584">The only limitation is that both shortcuts must contain the "Windows Logo" key (in addition to at least another key).</span></span>

- <span data-ttu-id="9d11a-585">Démarrez avec Windows : l’application peut être configurée pour démarrer automatiquement avec Windows.</span><span class="sxs-lookup"><span data-stu-id="9d11a-585">Start with Windows: The application can be configured to start automatically with Windows.</span></span>

### <a name="examples"></a><span data-ttu-id="9d11a-586">範例</span><span class="sxs-lookup"><span data-stu-id="9d11a-586">Examples</span></span>

<span data-ttu-id="9d11a-587">La figure ci-dessous illustre comment appeler ou envoyer un message instantané à un autre agent en cliquant avec le bouton droit sur le contact dans le volet de droite.</span><span class="sxs-lookup"><span data-stu-id="9d11a-587">The figure below illustrates how to call or send an IM to another agent by right-clicking the contact in the right pane.</span></span>

![Passer un appel ou envoyer un message instantané.](../media/Reskit_2012_Tools_Documentation_Image39.JPG)

<span data-ttu-id="9d11a-589">La figure ci-dessous illustre la manière dont Response Group agent Live affiche le nombre actuel d’appels dans la file d’attente et le délai d’attente le plus long parmi tous les appels entrants.</span><span class="sxs-lookup"><span data-stu-id="9d11a-589">The figure below illustrates how Response Group Agent Live displays the current number of calls in the queue and the longest waiting time among all these incoming calls.</span></span>

![Affichage des informations de file d’attente.](../media/Reskit_2012_Tools_Documentation_Image40.JPG)

### <a name="summary"></a><span data-ttu-id="9d11a-591">Résumé</span><span class="sxs-lookup"><span data-stu-id="9d11a-591">Summary</span></span>

<span data-ttu-id="9d11a-592">La connexion et la déconnexion rapides, l’appartenance à un groupe et les statistiques en temps réel de base sont des fonctionnalités intéressantes de l’agent Response Group qui ne sont disponibles qu’en dehors de l’application à partir du service Response Group.</span><span class="sxs-lookup"><span data-stu-id="9d11a-592">Fast sign-in and sign-out, group membership, and basic real-time statistics are interesting Response Group agent features that are only available outside the application from the Response Group service.</span></span> <span data-ttu-id="9d11a-593">Avec l’outil Response Group agent Live Resource Kit, les administrateurs de Skype entreprise Server 2015 peuvent fournir à leurs agents une application Windows qui leur permet d’effectuer des tâches de manière plus rapide et graphique.</span><span class="sxs-lookup"><span data-stu-id="9d11a-593">With the Response Group Agent Live Resource Kit tool, Skype for Business Server 2015 administrators can provide their agents with a Windows application that allows them to perform tasks in a faster and graphical way.</span></span>

## <a name="sefautil"></a><span data-ttu-id="9d11a-594">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="9d11a-594">SEFAUtil</span></span>
<span data-ttu-id="9d11a-595"><a name="SEFAUtil"> </a></span><span class="sxs-lookup"><span data-stu-id="9d11a-595"><a name="SEFAUtil"> </a></span></span>

<span data-ttu-id="9d11a-596">SEFAUtil (Secondary Extension Feature activation) est un outil de ligne de commande qui permet aux administrateurs de logiciels de communications Skype entreprise Server 2015 de configurer la sonnerie des délégués, le transfert d’appel, la sonnerie simultanée, Team-paramètres d’appel et prise d’appel de groupe pour le compte d’un utilisateur de Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9d11a-596">SEFAUtil (secondary extension feature activation) is a command-line tool that enables Skype for Business Server 2015 communications software administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Skype for Business Server 2015 user.</span></span> <span data-ttu-id="9d11a-597">L’outil permet également aux administrateurs d’interroger les paramètres de routage des appels publiés pour un utilisateur particulier. L’outil SEFAUtil permet à l’administrateur d’activer/de désactiver/modifier le transfert d’appel ou de sonner simultanément au nom de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9d11a-597">The tool also allows administrators to query the call-routing settings that are published for a particular user.The SEFAUtil tool allows the administrator to enable/disable/modify call forwarding or simultaneously ringing on behalf of the user.</span></span> <span data-ttu-id="9d11a-598">L’administrateur peut spécifier la cible (sous la forme d’un URI SIP) ou utiliser une cible qui a déjà été publiée par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9d11a-598">The administrator can specify the target (in the form of a SIP URI) or use a target that has already been published by the user.</span></span> <span data-ttu-id="9d11a-599">Cet outil permet également aux administrateurs d’ajouter ou de supprimer des délégués ou des membres du groupe d’appel d’équipe au nom de l’utilisateur. Cet outil est basé sur Microsoft Unified Communications Managed API (UCMA) 3,0 et exige que les administrateurs créent une application approuvée dans le magasin central de gestion pour SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="9d11a-599">This tool also allows administrators to add or remove delegates or team-call group members on behalf of the user.This tool is built on Microsoft Unified Communications Managed API (UCMA) 3.0 and requires that administrators create a trusted application in the Central Management store for SEFAUtil.</span></span>

<span data-ttu-id="9d11a-600">SEFAUtil (activation de la fonctionnalité d’extension secondaire) permet aux administrateurs et aux agents du support technique Skype entreprise Server 2015 de configurer la sonnerie de délégué, le transfert d’appel, la sonnerie simultanée, les paramètres d’appel d’équipe et la prise d’appel de groupe pour le compte de Skype pour l’utilisateur de Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9d11a-600">SEFAUtil (secondary extension feature activation) enables Skype for Business Server 2015 administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Skype for Business Server 2015 user.</span></span> <span data-ttu-id="9d11a-601">Cet outil permet également aux administrateurs d’interroger les paramètres de routage des appels publiés pour un utilisateur particulier.</span><span class="sxs-lookup"><span data-stu-id="9d11a-601">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span>

### <a name="description"></a><span data-ttu-id="9d11a-602">Description</span><span class="sxs-lookup"><span data-stu-id="9d11a-602">Description</span></span>

<span data-ttu-id="9d11a-603">La version actuelle de SEFAUtil n’est qu’un outil de ligne de commande ; Il n’y a pas d’interface utilisateur graphique de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="9d11a-603">The current version of SEFAUtil is only a command-line tool; there is no supporting graphical user interface.</span></span> <span data-ttu-id="9d11a-604">Cet outil est basé sur Microsoft Unified Communications Managed API (UCMA) 3,0.</span><span class="sxs-lookup"><span data-stu-id="9d11a-604">This tool is based on Microsoft Unified Communications Managed API (UCMA) 3.0.</span></span> <span data-ttu-id="9d11a-605">Les fonctionnalités de cet outil permettent aux administrateurs et aux agents du support technique d’effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="9d11a-605">The features in this tool allow administrators and helpdesk agents to do the following:</span></span>

- <span data-ttu-id="9d11a-606">Afficher tous les paramètres de routage des appels d’un utilisateur (inclut le transfert d’appels, la délégation, la sonnerie simultanée, l’appel d’équipe et la prise d’appel de groupe)</span><span class="sxs-lookup"><span data-stu-id="9d11a-606">View all call routing settings for a user (includes call-forwarding, delegation, simultaneous ringing, team-call and group call pickup)</span></span>

- <span data-ttu-id="9d11a-607">Activer/désactiver/modifier le paramètre de transfert d’appel (y compris la destination et le minuteur de non-réponse)</span><span class="sxs-lookup"><span data-stu-id="9d11a-607">Enable/disable/modify call-forwarding setting (includes destination and no-answer timer)</span></span>

- <span data-ttu-id="9d11a-608">Activer/désactiver/modifier les configurations immédiates de transfert d’appel</span><span class="sxs-lookup"><span data-stu-id="9d11a-608">Enable/disable/modify call-forwarding immediate configurations</span></span>

- <span data-ttu-id="9d11a-609">Activer/désactiver/modifier les paramètres de délégation</span><span class="sxs-lookup"><span data-stu-id="9d11a-609">Enable/disable/modify delegation settings</span></span>

- <span data-ttu-id="9d11a-610">Activer/désactiver/modifier les paramètres du groupe d’appel d’équipe</span><span class="sxs-lookup"><span data-stu-id="9d11a-610">Enable/disable/modify team-call group settings</span></span>

    > [!NOTE]
    > <span data-ttu-id="9d11a-611">Nouveauté de l’outil SEFAUtil dans Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="9d11a-611">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

- <span data-ttu-id="9d11a-612">Activer/désactiver/modifier les paramètres de sonnerie simultanée (il s’agit de la destination)</span><span class="sxs-lookup"><span data-stu-id="9d11a-612">Enable/disable/modify simultaneous ringing settings (includes destination)</span></span>

    > [!NOTE]
    > <span data-ttu-id="9d11a-613">Nouveauté de l’outil SEFAUtil dans Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="9d11a-613">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

- <span data-ttu-id="9d11a-614">Activer/désactiver/modifier les paramètres de prise d’appel de groupe</span><span class="sxs-lookup"><span data-stu-id="9d11a-614">Enable/disable/modify group call pickup settings</span></span>

    > [!CAUTION]
    > <span data-ttu-id="9d11a-615">Nouveauté de l’outil SEFAUtil dans Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="9d11a-615">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

<span data-ttu-id="9d11a-616">Cet outil présente les limitations suivantes :</span><span class="sxs-lookup"><span data-stu-id="9d11a-616">This tool has the following limitations:</span></span>

- <span data-ttu-id="9d11a-617">Pris en charge uniquement pour les utilisateurs hébergés dans un pool Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="9d11a-617">Supported only for users homed in a Skype for Business Server pool</span></span>

- <span data-ttu-id="9d11a-618">La modification en bloc des paramètres de routage des appels pour plusieurs utilisateurs n’est pas prise en charge</span><span class="sxs-lookup"><span data-stu-id="9d11a-618">Bulk-edit of call routing settings for several users is not supported</span></span>

### <a name="output"></a><span data-ttu-id="9d11a-619">Output</span><span class="sxs-lookup"><span data-stu-id="9d11a-619">Output</span></span>

<span data-ttu-id="9d11a-620">La version actuelle de cet outil fournit uniquement des résultats dans la fenêtre d’invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="9d11a-620">The current version of this tool provides output only in the Command Prompt window.</span></span> <span data-ttu-id="9d11a-621">Pour plus d’informations, consultez la section exemples plus loin dans ce document.</span><span class="sxs-lookup"><span data-stu-id="9d11a-621">For details, see the Examples section later in this document.</span></span>

### <a name="purpose"></a><span data-ttu-id="9d11a-622">Objectif</span><span class="sxs-lookup"><span data-stu-id="9d11a-622">Purpose</span></span>

<span data-ttu-id="9d11a-623">Voici quelques-uns des principaux scénarios dans lesquels cet outil peut être utilisé :</span><span class="sxs-lookup"><span data-stu-id="9d11a-623">Following are some of the key scenarios where this tool may be used:</span></span>

- <span data-ttu-id="9d11a-624">Bob est un cadre et a été déplacé vers Skype entreprise Server Telephony.</span><span class="sxs-lookup"><span data-stu-id="9d11a-624">Bob is an executive and has been moved to Skype for Business Server telephony.</span></span> <span data-ttu-id="9d11a-625">Il dispose d’une délégation sur son système PBX existant.</span><span class="sxs-lookup"><span data-stu-id="9d11a-625">He has delegation on his existing PBX system.</span></span> <span data-ttu-id="9d11a-626">Dans le cadre de la migration vers Skype entreprise Server 2015, l’administrateur peut configurer le routage de Bob afin de refléter sa configuration de délégation préexistante.</span><span class="sxs-lookup"><span data-stu-id="9d11a-626">As part of the move to Skype for Business Server 2015, the administrator is able to configure Bob's routing to reflect his pre-existing delegation configuration.</span></span>

- <span data-ttu-id="9d11a-627">Alice se rend compte qu’elle attend un appel important de la part de l’un de ses clients.</span><span class="sxs-lookup"><span data-stu-id="9d11a-627">Alice is travelling and realizes that she is expecting an important call from one of her customers.</span></span> <span data-ttu-id="9d11a-628">Toutefois, elle se trouve dans un hôtel et n’a pas accès à un ordinateur.</span><span class="sxs-lookup"><span data-stu-id="9d11a-628">However, she is in a hotel and has no access to a computer.</span></span> <span data-ttu-id="9d11a-629">Elle appelle le support technique et demande à son numéro de téléphone mobile tous les appels effectués sur son numéro de travail.</span><span class="sxs-lookup"><span data-stu-id="9d11a-629">She calls the helpdesk and requests that they forward to her mobile number all the calls made to her work number.</span></span> <span data-ttu-id="9d11a-630">Le personnel du support technique peut effectuer la configuration en son nom.</span><span class="sxs-lookup"><span data-stu-id="9d11a-630">The helpdesk personnel are able to do the configuration on her behalf.</span></span>

- <span data-ttu-id="9d11a-631">Les appels de Jean vers son numéro de travail accédant à sa messagerie vocale mobile chaque fois qu’il travaille ; Toutefois, les choses semblent fonctionner correctement dans la plupart des autres emplacements.</span><span class="sxs-lookup"><span data-stu-id="9d11a-631">Joe's calls to his work number are going to his mobile voicemail whenever he is at work; however, things appear to be working correctly in most other locations.</span></span> <span data-ttu-id="9d11a-632">Le technicien du service d’assistance peut consulter la configuration de routage de Joe et se dévoiler que Joe a une sonnerie simultanée configurée sur son téléphone mobile.</span><span class="sxs-lookup"><span data-stu-id="9d11a-632">The helpdesk technician is able to view Joe's routing configuration and discovers that Joe has simultaneous ringing configured to his mobile phone.</span></span> <span data-ttu-id="9d11a-633">Le technicien demande à Joe la couverture mobile au niveau de son bureau et est en mesure de déterminer que la règle de sonnerie simultanée est ce qui provoque l’accès des appels à la messagerie vocale mobile de Jean quand sa couverture réseau est médiocre.</span><span class="sxs-lookup"><span data-stu-id="9d11a-633">The technician asks Joe about the mobile coverage at his office and is able to determine that the simultaneous ringing rule is what is causing the calls to go to Joe's mobile voicemail when his network coverage is poor.</span></span>

- <span data-ttu-id="9d11a-634">Mike est un nouvel employé chez contoso et il rejoint une nouvelle équipe sur laquelle tous les membres sont configurés pour l’appel d’équipe, lorsqu’il est activé pour Skype entreprise Server 2015, l’administrateur peut définir ses paramètres de groupe d’appel d’équipe afin d’inclure tous ses nouveaux membres d’équipe. par ailleurs, l’administrateur ajoute Mike en tant que membre du groupe d’appel d’équipe pour chacun des membres de son équipe.</span><span class="sxs-lookup"><span data-stu-id="9d11a-634">Mike is a new employee at Contoso and he's joining a new team on which all members are configured for team-call, when being enabled for Skype for Business Server 2015, the administrator is able to set his team-call group settings to include all his new team members, additionally, the administrator adds Mike as a team-call group member for each of the members in his team.</span></span>

- <span data-ttu-id="9d11a-635">Une pratique de service clientèle dans le département des ressources humaines de contoso est de fournir un service personnel à tous les appelants depuis le premier appel.</span><span class="sxs-lookup"><span data-stu-id="9d11a-635">A customer service practice in the human resources department at Contoso is to provide personal service for all callers since the first call.</span></span> <span data-ttu-id="9d11a-636">Étant donné que tous les membres du service se sont très proches l’un de l’autre, le fait que tous les téléphones sonnent en même temps avec l’appel d’équipe est très gênant pour l’équipe.</span><span class="sxs-lookup"><span data-stu-id="9d11a-636">Given that all members of the department sit very close to each other, having all phones ringing at the same time with team-call is very disruptive for the team.</span></span> <span data-ttu-id="9d11a-637">Pour fournir le meilleur service sans interrompre les membres de l’équipe, l’administrateur de Skype entreprise Server 2015 tire parti de la fonctionnalité de prise d’appel de groupe.</span><span class="sxs-lookup"><span data-stu-id="9d11a-637">To provide the best service without disrupting the team members, the Skype for Business Server 2015 administrator takes advantage of the Group Call Pickup capability.</span></span> <span data-ttu-id="9d11a-638">L’administrateur ajoute tous les membres du service à un groupe de collecte et communique au service le numéro du groupe de collecte.</span><span class="sxs-lookup"><span data-stu-id="9d11a-638">The administrator adds all department members to a pickup group and communicates to the department the pickup group number.</span></span> <span data-ttu-id="9d11a-639">Lorsque Samantha est absent de son bureau, Jean remarque son sonnerie et il répond à l’appel de son bureau.</span><span class="sxs-lookup"><span data-stu-id="9d11a-639">When Samantha is absent from her desk, Joe notices her phone ringing and he proceeds to answer the call from his desk.</span></span>

### <a name="requirements"></a><span data-ttu-id="9d11a-640">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="9d11a-640">Requirements</span></span>

<span data-ttu-id="9d11a-641">L’outil SEFAUtil peut être exécuté uniquement sur un ordinateur qui fait partie d’un pool d’applications approuvées.</span><span class="sxs-lookup"><span data-stu-id="9d11a-641">The SEFAUtil tool can be run only on a computer that is a part of a Trusted Application Pool.</span></span> <span data-ttu-id="9d11a-642">UCMA 3,0 doit être installé sur cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="9d11a-642">UCMA 3.0 must be installed on that computer.</span></span> <span data-ttu-id="9d11a-643">Pour exécuter l’outil, une nouvelle application approuvée avec l’ID d’application SEFAUtil doit être créée sur ce pool.</span><span class="sxs-lookup"><span data-stu-id="9d11a-643">To run the tool, a new Trusted Application with the SEFAUtil application ID must be created on that pool.</span></span>

### <a name="creating-a-new-trusted-application-for-the-sefautil-tool"></a><span data-ttu-id="9d11a-644">Création d’une application approuvée pour l’outil SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="9d11a-644">Creating a new Trusted Application for the SEFAUtil tool</span></span>

1. <span data-ttu-id="9d11a-645">L’outil SEFAUTil peut être exécuté uniquement sur un ordinateur qui fait partie d’un pool d’applications approuvées.</span><span class="sxs-lookup"><span data-stu-id="9d11a-645">The SEFAUTil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="9d11a-646">Si nécessaire, l’ajout d’un pool en tant que nouveau pool d’applications approuvées peut être réalisé via Skype entreprise Server Management Shell avec l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="9d11a-646">If needed, adding a pool as a new trusted application pool can be done via the Skype for Business Server Management Shell with the following cmdlet:</span></span>

   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

    > [!NOTE]
    > <span data-ttu-id="9d11a-647">UCMA 3,0 doit être installé sur tout ordinateur qui sera utilisé pour exécuter l’outil SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="9d11a-647">UCMA 3.0 must be installed on any computer that will be used to run the SEFAUtil tool.</span></span>

2. <span data-ttu-id="9d11a-648">Une application approuvée doit être définie dans la topologie pour l’outil SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="9d11a-648">A trusted application needs to be defined in the topology for the SEFAUtil tool.</span></span> <span data-ttu-id="9d11a-649">Pour définir SEFAUtil en tant que nouvelle application approuvée, utilisez Skype entreprise Server Management Shell et exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="9d11a-649">To define SEFAUtil as a new trusted application, use the Skype for Business Server Management Shell and execute the following cmdlet:</span></span>

   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN> -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="9d11a-650">Un autre port peut être utilisé si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="9d11a-650">A different port can be used if needed.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9d11a-651">Nom de domaine complet du pool : nom de domaine complet (FQDN) du serveur ou du pool qui hébergera l’application SEFAUtil (généralement un serveur frontal Skype entreprise > ou un pool).</span><span class="sxs-lookup"><span data-stu-id="9d11a-651">Pool FQDN: The FQDN of the server or pool that will host the SEFAUtil application (usually a Skype for Business Front End server     > or pool).</span></span>
    > <span data-ttu-id="9d11a-652">Nom de domaine complet du serveur d’inscriptions de pool : nom de domaine complet du serveur ou pool de serveurs frontaux Skype entreprise associé à ce pool d’applications.</span><span class="sxs-lookup"><span data-stu-id="9d11a-652">Pool Registrar FQDN: The FQDN of the Skype for Business Front End server or pool associated with this application pool.</span></span>
    > <span data-ttu-id="9d11a-653">Site de pool : ID de site du site sur lequel ce pool est hébergé.</span><span class="sxs-lookup"><span data-stu-id="9d11a-653">Pool Site: The Site ID of the site on which this pool is homed.</span></span>

3. <span data-ttu-id="9d11a-654">Les modifications de la topologie doivent être activées.</span><span class="sxs-lookup"><span data-stu-id="9d11a-654">The topology changes need to be enabled.</span></span> <span data-ttu-id="9d11a-655">L’activation des modifications de la topologie peut être réalisée via Skype entreprise Server Management Shell en exécutant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="9d11a-655">Enabling the topology changes can be done via the Skype for Business Server Management Shell by executing the following cmdlet:</span></span>

   ```powershell
   Enable-CsToplogy
   ```

4. <span data-ttu-id="9d11a-656">Si nécessaire, installez les outils du kit de ressources Skype entreprise Server 2015 sur le serveur qui sera utilisé pour exécuter l’outil SEFAUtil (le serveur doit faire partie d’un pool d’applications approuvées).</span><span class="sxs-lookup"><span data-stu-id="9d11a-656">If needed, install the Skype for Business Server 2015 Resource Kit Tools in the server that will be used to run the SEFAUtil tool (the server must be part of a trusted application pool).</span></span>

5. <span data-ttu-id="9d11a-657">Vérifiez que le SEFAUtil s’exécute correctement.</span><span class="sxs-lookup"><span data-stu-id="9d11a-657">Verify the SEFAUtil is running correctly.</span></span> <span data-ttu-id="9d11a-658">Pour ce faire, exécutez l’outil à partir d’une invite de commande Windows avec des privilèges d’administrateur pour afficher les paramètres de transfert d’appel d’un utilisateur dans le déploiement.</span><span class="sxs-lookup"><span data-stu-id="9d11a-658">To do this, run the tool from a windows command prompt with administrator privileges to display the call forwarding settings of a user in the deployment.</span></span> <span data-ttu-id="9d11a-659">Par défaut, l’outil se trouve dans : ". ..\Program Files\Skype pour Business Server 2015 \ reskit".</span><span class="sxs-lookup"><span data-stu-id="9d11a-659">By default the tool will be located in: "…\Program Files\Skype for Business Server 2015\Reskit".</span></span> <span data-ttu-id="9d11a-660">Pour afficher les paramètres de transfert d’appel d’un utilisateur, utilisez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="9d11a-660">To display the call forwarding settings of a user, use the following command:</span></span>

   ```console
   SEFAUtil.exe <user SIP address> /server:<Skype for Business Server/Pool FQDN>
   ```

    <span data-ttu-id="9d11a-661">Les paramètres de transfert d’appel de l’utilisateur doivent être affichés.</span><span class="sxs-lookup"><span data-stu-id="9d11a-661">The call forwarding settings of the user should be displayed.</span></span>

#### <a name="group-call-pickup"></a><span data-ttu-id="9d11a-662">Prise d’appel de groupe</span><span class="sxs-lookup"><span data-stu-id="9d11a-662">Group Call Pickup</span></span>

<span data-ttu-id="9d11a-663">La prise d’appel de groupe nécessite une configuration supplémentaire dans Skype entreprise Server 2015 pour être entièrement activée.</span><span class="sxs-lookup"><span data-stu-id="9d11a-663">Group Call Pickup requires additional configuration in Skype for Business Server 2015 for the capability to be fully enabled.</span></span> <span data-ttu-id="9d11a-664">Avant d’affecter des groupes de collecte aux utilisateurs, reportez-vous à la documentation du produit de prise d’appel de groupe pour les étapes de planification et de déploiement de cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="9d11a-664">Before assigning pickup groups to users, refer to the Group Call Pickup product documentation for the planning and deployment steps of this capability.</span></span>

### <a name="examples"></a><span data-ttu-id="9d11a-665">範例</span><span class="sxs-lookup"><span data-stu-id="9d11a-665">Examples</span></span>

#### <a name="display-current-call-handling-settings"></a><span data-ttu-id="9d11a-666">Afficher les paramètres de gestion des appels actifs</span><span class="sxs-lookup"><span data-stu-id="9d11a-666">Display Current Call Handling Settings</span></span>

<span data-ttu-id="9d11a-667">La commande suivante affiche le traitement des appels pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9d11a-667">The following command displays the call handling for the user.</span></span>  `SEFAUtil.exe /server:SfBS2015server.contoso.com katarina@contoso.com`

> [!NOTE]
> <span data-ttu-id="9d11a-668">Cet exemple utilise le commutateur **/Server** pour spécifier le serveur Skype entreprise auquel se connecter.</span><span class="sxs-lookup"><span data-stu-id="9d11a-668">This example uses the **/server** switch to specify the Skype for Business Server to connect to.</span></span>

 <span data-ttu-id="9d11a-669">**Résultat**</span><span class="sxs-lookup"><span data-stu-id="9d11a-669">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:20
Call Forward No Answer to: voicemail
```

#### <a name="set-the-call-forwardno-answer-destination"></a><span data-ttu-id="9d11a-670">Définir la destination de transfert d’appel/pas de réponse</span><span class="sxs-lookup"><span data-stu-id="9d11a-670">Set the Call Forward/No Answer Destination</span></span>

<span data-ttu-id="9d11a-671">Cet exemple montre comment définir la destination de transfert d’appel/de réponse et le retard de l’anneau.</span><span class="sxs-lookup"><span data-stu-id="9d11a-671">This example sets the call forward/no answer destination and the ring delay.</span></span> <span data-ttu-id="9d11a-672">Ici, le commutateur/Server n’est pas fourni ; SEFAUtil tente de découvrir automatiquement le service Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9d11a-672">Here, the /server switch is not provided; SEFAUtil attempts to autodiscover the Skype for Business Server 2015.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone
```

 <span data-ttu-id="9d11a-673">**Résultat**</span><span class="sxs-lookup"><span data-stu-id="9d11a-673">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="enable-call-forwarding-immediately"></a><span data-ttu-id="9d11a-674">Activer le transfert d’appel immédiatement</span><span class="sxs-lookup"><span data-stu-id="9d11a-674">Enable Call Forwarding Immediately</span></span>

<span data-ttu-id="9d11a-675">Cet exemple active immédiatement le transfert d’appel à un autre utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9d11a-675">This example immediately enables call-forwarding to another user.</span></span>

```console
SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com
```

 <span data-ttu-id="9d11a-676">**Résultat**</span><span class="sxs-lookup"><span data-stu-id="9d11a-676">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Forward immediate to: sip:anders@contoso.com
```

#### <a name="disable-call-forwarding-immediately"></a><span data-ttu-id="9d11a-677">Désactiver immédiatement le transfert d’appel</span><span class="sxs-lookup"><span data-stu-id="9d11a-677">Disable Call Forwarding Immediately</span></span>

<span data-ttu-id="9d11a-678">Cet exemple désactive immédiatement le transfert d’appel.</span><span class="sxs-lookup"><span data-stu-id="9d11a-678">This example immediately disables call forwarding.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com katarina@contoso.com  /disablefwdimmediate
```

 <span data-ttu-id="9d11a-679">**Résultat**</span><span class="sxs-lookup"><span data-stu-id="9d11a-679">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a><span data-ttu-id="9d11a-680">Ajouter un utilisateur en tant que délégué et configurer la sonnerie simultanée des délégués</span><span class="sxs-lookup"><span data-stu-id="9d11a-680">Add a User as a Delegate and Set Up Simultaneous Ringing of Delegates</span></span>

<span data-ttu-id="9d11a-681">Cet exemple ajoute un utilisateur en tant que délégué et configure la sonnerie simultanée des délégués.</span><span class="sxs-lookup"><span data-stu-id="9d11a-681">This example adds a user as a delegate and sets up simultaneous ringing of delegates.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates
```

 <span data-ttu-id="9d11a-682">**Résultat**</span><span class="sxs-lookup"><span data-stu-id="9d11a-682">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simultaneously Ringing Delegates: sip:joe@contoso.com
```

#### <a name="change-simultaneous-ringing-rule-of-delegates"></a><span data-ttu-id="9d11a-683">Modifier la règle de sonnerie simultanée des délégués</span><span class="sxs-lookup"><span data-stu-id="9d11a-683">Change Simultaneous Ringing Rule of Delegates</span></span>

<span data-ttu-id="9d11a-684">Cet exemple montre comment remplacer la règle de sonnerie simultanée définie dans l’exemple précédent par la règle de sonnerie différée.</span><span class="sxs-lookup"><span data-stu-id="9d11a-684">This example changes the simultaneous ringing rule that was set in the previous example to the delayed ringing rule.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10
```

 <span data-ttu-id="9d11a-685">**Résultat**</span><span class="sxs-lookup"><span data-stu-id="9d11a-685">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com
```

#### <a name="remove-the-delegate"></a><span data-ttu-id="9d11a-686">Supprimer le délégué</span><span class="sxs-lookup"><span data-stu-id="9d11a-686">Remove the Delegate</span></span>

<span data-ttu-id="9d11a-687">Cet exemple supprime le délégué.</span><span class="sxs-lookup"><span data-stu-id="9d11a-687">This example removes the delegate.</span></span>

> [!NOTE]
> <span data-ttu-id="9d11a-688">Lorsque le dernier délégué est supprimé, la sonnerie de délégué est automatiquement désactivée.</span><span class="sxs-lookup"><span data-stu-id="9d11a-688">When the last delegate is removed, delegate ringing is automatically disabled.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com
```

 <span data-ttu-id="9d11a-689">**Résultat**</span><span class="sxs-lookup"><span data-stu-id="9d11a-689">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a><span data-ttu-id="9d11a-690">Ajouter un délégué et configurer la règle appeler-transférer aux délégués</span><span class="sxs-lookup"><span data-stu-id="9d11a-690">Add a Delegate and Set Up the Call-Forward to Delegates Rule</span></span>

<span data-ttu-id="9d11a-691">Cet exemple ajoute un délégué et configure la règle appeler-forward to delegates.</span><span class="sxs-lookup"><span data-stu-id="9d11a-691">This example adds a delegate and sets up the call-forward to delegates rule.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates
```

 <span data-ttu-id="9d11a-692">**Résultat**</span><span class="sxs-lookup"><span data-stu-id="9d11a-692">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Forwarding calls to Delegates: sip:anders@contoso.com
```

#### <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a><span data-ttu-id="9d11a-693">Activer la sonnerie simultanée et définir un numéro de destination</span><span class="sxs-lookup"><span data-stu-id="9d11a-693">Enable Simultaneous Ringing and Set a Destination Number</span></span>

<span data-ttu-id="9d11a-694">Cet exemple montre comment activer la sonnerie simultanée et définir un numéro de destination de sonnerie simultanée.</span><span class="sxs-lookup"><span data-stu-id="9d11a-694">This example enables simultaneous ringing and sets a simultaneous ringing destination number.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring
```

> [!NOTE]
> <span data-ttu-id="9d11a-695">Pour modifier le numéro de destination de la sonnerie simultanée d’un utilisateur pour lequel la sonnerie simultanée est déjà activée, conservez la commande avec le commutateur/enablesimulring, sinon le numéro de destination ne sera pas modifié.</span><span class="sxs-lookup"><span data-stu-id="9d11a-695">To change the simultaneous ringing destination number of a user that has already simultaneous ringing enabled, keep the command with the /enablesimulring switch, otherwise the destination number will not be changed.</span></span>

 <span data-ttu-id="9d11a-696">**Résultat**</span><span class="sxs-lookup"><span data-stu-id="9d11a-696">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: True
Simul_Ringing to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="disable-simultaneous-ringing"></a><span data-ttu-id="9d11a-697">Désactiver la sonnerie simultanée</span><span class="sxs-lookup"><span data-stu-id="9d11a-697">Disable Simultaneous Ringing</span></span>

<span data-ttu-id="9d11a-698">Cet exemple montre comment désactiver la sonnerie simultanée.</span><span class="sxs-lookup"><span data-stu-id="9d11a-698">This example disables simultaneous ringing.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablesimulring
```

 <span data-ttu-id="9d11a-699">**Résultat**</span><span class="sxs-lookup"><span data-stu-id="9d11a-699">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a><span data-ttu-id="9d11a-700">Ajouter un membre d’équipe pour Team-Call et configurer la sonnerie simultanée pour le groupe membres d’appel d’équipe</span><span class="sxs-lookup"><span data-stu-id="9d11a-700">Add a Team Member for Team-Call and Set up Simultaneous Ringing to the Team-Call Members Group</span></span>

<span data-ttu-id="9d11a-701">Cet exemple ajoute un membre d’équipe au groupe d’appel d’équipe d’un utilisateur et active la sonnerie simultanée pour le groupe d’appel d’équipe.</span><span class="sxs-lookup"><span data-stu-id="9d11a-701">This example adds a team member to the team-call group of a user and enables simultaneous ringing to the team-call group.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam
```

> [!NOTE]
> <span data-ttu-id="9d11a-702">L’ajout d’un membre au groupe d’appel d’équipe d’un utilisateur bascule automatiquement la simultanée de sonnerie simultanée des utilisateurs vers sonnerie simultanée son groupe d’appel d’équipe.</span><span class="sxs-lookup"><span data-stu-id="9d11a-702">Adding a member to the team-call group of a user will automatically switch the simultaneous ringing settigs of the users to simulring his team-call group.</span></span>

 <span data-ttu-id="9d11a-703">**Résultat**</span><span class="sxs-lookup"><span data-stu-id="9d11a-703">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Team ringing enabled. Team: sip:anders@contoso.com
```

#### <a name="remove-a-member-from-the-team-call-group"></a><span data-ttu-id="9d11a-704">Supprimer un membre du groupe d’appel d’équipe</span><span class="sxs-lookup"><span data-stu-id="9d11a-704">Remove a Member from the Team-Call Group</span></span>

<span data-ttu-id="9d11a-705">Cet exemple supprime un membre d’équipe du groupe d’appel d’équipe d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9d11a-705">This example removes a team member of the team-call group of a user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com
```

> [!NOTE]
> <span data-ttu-id="9d11a-706">Si le membre supprimé est le seul membre du groupe d’appel d’équipe, la sonnerie simultanée du groupe d’appel d’équipe est automatiquement désactivée.</span><span class="sxs-lookup"><span data-stu-id="9d11a-706">If the member being removed is the only member of the team-call group, simultaneously ringing to the team-call group will be automatically disabled.</span></span>

 <span data-ttu-id="9d11a-707">**Résultat**</span><span class="sxs-lookup"><span data-stu-id="9d11a-707">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="set-the-delayed-ring-to-the-team-call-group"></a><span data-ttu-id="9d11a-708">Définir la sonnerie différée sur le groupe d’appel d’équipe</span><span class="sxs-lookup"><span data-stu-id="9d11a-708">Set the Delayed Ring to the Team-Call Group</span></span>

<span data-ttu-id="9d11a-709">Cet exemple montre comment modifier la sonnerie différée en définissant le paramètre de l’heure du groupe d’appels d’équipe.</span><span class="sxs-lookup"><span data-stu-id="9d11a-709">This example changes the delayed ring to the team-call group time setting.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringteam:5
```

 <span data-ttu-id="9d11a-710">**Résultat**</span><span class="sxs-lookup"><span data-stu-id="9d11a-710">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com
```

#### <a name="enable-team-call"></a><span data-ttu-id="9d11a-711">Activer l’appel d’équipe</span><span class="sxs-lookup"><span data-stu-id="9d11a-711">Enable Team-Call</span></span>

<span data-ttu-id="9d11a-712">Cet exemple montre comment activer un appel d’équipe pour un utilisateur donné.</span><span class="sxs-lookup"><span data-stu-id="9d11a-712">This example enables team-call for a given user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /simulringteam
```

> [!NOTE]
> <span data-ttu-id="9d11a-713">Si le groupe d’appel d’équipe de l’utilisateur ne possède pas de membres, Team-Call n’est pas activé.</span><span class="sxs-lookup"><span data-stu-id="9d11a-713">If the team-call group of the user has no members, team-call won't be enabled.</span></span>

 <span data-ttu-id="9d11a-714">**Résultat**</span><span class="sxs-lookup"><span data-stu-id="9d11a-714">**Output**</span></span>

#### <a name="disable-team-call"></a><span data-ttu-id="9d11a-715">Désactiver l’appel d’équipe</span><span class="sxs-lookup"><span data-stu-id="9d11a-715">Disable Team-Call</span></span>

<span data-ttu-id="9d11a-716">Cet exemple désactive l’appel d’équipe pour un utilisateur donné.</span><span class="sxs-lookup"><span data-stu-id="9d11a-716">This example disables team-call for a given user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disableteamcall
```

 <span data-ttu-id="9d11a-717">**Résultat**</span><span class="sxs-lookup"><span data-stu-id="9d11a-717">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a><span data-ttu-id="9d11a-718">Activer la prise d’appel de groupe et attribuer un groupe de prise d’appel à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="9d11a-718">Enable Group Call Pickup and Assign a Pickup Group to a User</span></span>

<span data-ttu-id="9d11a-719">Cet exemple attribue un groupe de prise d’appel à un utilisateur et active la prise d’appel de groupe.</span><span class="sxs-lookup"><span data-stu-id="9d11a-719">This example assigns a pickup group to a user and enables Group Call Pickup.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199
```

 <span data-ttu-id="9d11a-720">**Résultat**</span><span class="sxs-lookup"><span data-stu-id="9d11a-720">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone
```

#### <a name="disable-group-call-pickup"></a><span data-ttu-id="9d11a-721">Désactiver la prise d’appel de groupe</span><span class="sxs-lookup"><span data-stu-id="9d11a-721">Disable Group Call Pickup</span></span>

<span data-ttu-id="9d11a-722">Cet exemple désactive la prise d’appel de groupe pour un utilisateur donné.</span><span class="sxs-lookup"><span data-stu-id="9d11a-722">This example disables Group Call Pickup for a given user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablegrouppickup
```

> [!NOTE]
> <span data-ttu-id="9d11a-723">Lorsque vous désactivez la prise d’appel de groupe pour un utilisateur, le numéro de groupe qui a été attribué à l’utilisateur n’est pas conservé.</span><span class="sxs-lookup"><span data-stu-id="9d11a-723">When you disable Group Call Pickup for a user, the group number that was assigned to the user is not retained.</span></span> <span data-ttu-id="9d11a-724">Si vous souhaitez ensuite réactiver la prise d’appel de groupe pour cet utilisateur, vous devez réaffecter le numéro de groupe avec le commutateur/enablegrouppickup.</span><span class="sxs-lookup"><span data-stu-id="9d11a-724">If you subsequently want to re-enable Group Call Pickup for that user, you must assign the group number again with the /enablegrouppickup switch.</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
```

## <a name="sysprepps1"></a><span data-ttu-id="9d11a-725">SYSPrep. ps1</span><span class="sxs-lookup"><span data-stu-id="9d11a-725">SYSPrep.ps1</span></span>
<span data-ttu-id="9d11a-726"><a name="SYSPrep"> </a></span><span class="sxs-lookup"><span data-stu-id="9d11a-726"><a name="SYSPrep"> </a></span></span>

### <a name="description"></a><span data-ttu-id="9d11a-727">Description</span><span class="sxs-lookup"><span data-stu-id="9d11a-727">Description</span></span>

<span data-ttu-id="9d11a-728">SYSPrep. ps1 est un script Windows PowerShell qui installe les éléments prérequis de Skype entreprise Server 2015 suivants sur votre système d’exploitation Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="9d11a-728">SYSPrep.ps1 is a Windows PowerShell script that will install the following Skype for Business Server 2015 prerequisites on your Windows Server 2008 operating system machine.</span></span>

- <span data-ttu-id="9d11a-729">Microsoft .NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="9d11a-729">Microsoft .Net Framework 4.5</span></span>

- <span data-ttu-id="9d11a-730">Microsoft SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="9d11a-730">Microsoft SQL Server Express</span></span>

- <span data-ttu-id="9d11a-731">Windows PowerShell version 3,0</span><span class="sxs-lookup"><span data-stu-id="9d11a-731">Windows Powershell version 3.0</span></span>

- <span data-ttu-id="9d11a-732">Visual C++ 2010 Redistributable</span><span class="sxs-lookup"><span data-stu-id="9d11a-732">Visual C++ 2010 Redistributable</span></span>

- <span data-ttu-id="9d11a-733">Mises à jour de Internet Information Server</span><span class="sxs-lookup"><span data-stu-id="9d11a-733">Internet Information Server Updates</span></span>

- <span data-ttu-id="9d11a-734">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="9d11a-734">Windows Identity Foundation</span></span>

- <span data-ttu-id="9d11a-735">Fichiers principaux de Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="9d11a-735">Skype for Business Server 2015 Core files</span></span>

  <span data-ttu-id="9d11a-736">Bien que le nom du script soit semblable à l’outil de préparation du système pour les systèmes d’exploitation Microsoft Windows, ils sont différents.</span><span class="sxs-lookup"><span data-stu-id="9d11a-736">While the script name is similar to the System Preparation Tool for the Microsoft Windows operating systems, they are different.</span></span> <span data-ttu-id="9d11a-737">Ce script installe uniquement les composants requis pour Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9d11a-737">This script will only install the required prerequisites for Skype for Business Server 2015.</span></span> <span data-ttu-id="9d11a-738">Une fois ces éléments prérequis installés, l’outil SYSPrep Windows peut ensuite être utilisé pour créer une image du serveur.</span><span class="sxs-lookup"><span data-stu-id="9d11a-738">Once those prerequisites are installed, the Windows SYSPrep tool can then be used to create an image of the server.</span></span>

### <a name="requirements"></a><span data-ttu-id="9d11a-739">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="9d11a-739">Requirements</span></span>

<span data-ttu-id="9d11a-740">Avant d’exécuter le script SYSPrep. ps1, vous devez copier les fichiers prérequis dans un dossier local sur l’ordinateur du système d’exploitation Windows Server 2008 (par exemple **D:\setup)**.</span><span class="sxs-lookup"><span data-stu-id="9d11a-740">Prior to running the SYSPrep.ps1 script, you must copy the prerequisite files to a local folder on the Windows Server 2008 operating system machine (for example **D:\Setup)**.</span></span> <span data-ttu-id="9d11a-741">Ce dossier doit également inclure une copie des fichiers de Skype entreprise Server 2015, notamment **Setup. exe.**</span><span class="sxs-lookup"><span data-stu-id="9d11a-741">This folder must also include a copy of the Skype for Business Server 2015 files, specifically **Setup.exe.**</span></span> <span data-ttu-id="9d11a-742">Les fichiers prérequis peuvent être téléchargés à partir des emplacements suivants :</span><span class="sxs-lookup"><span data-stu-id="9d11a-742">The prerequisite files can be downloaded from the following locations:</span></span>


| <span data-ttu-id="9d11a-743">**Prérequis**</span><span class="sxs-lookup"><span data-stu-id="9d11a-743">**Prerequisite**</span></span>                                | <span data-ttu-id="9d11a-744">**Emplacement**</span><span class="sxs-lookup"><span data-stu-id="9d11a-744">**Location**</span></span>                                                            |
|:------------------------------------------------|:------------------------------------------------------------------------|
| <span data-ttu-id="9d11a-745">Microsoft .NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="9d11a-745">Microsoft .Net Framework 4.5</span></span>  <br/>             | <https://go.microsoft.com/?linkid=9816306>  <br/>                       |
| <span data-ttu-id="9d11a-746">Microsoft SQL Server Express 2008 R2</span><span class="sxs-lookup"><span data-stu-id="9d11a-746">Microsoft SQL Server Express 2008 R2</span></span>  <br/>     | <https://www.microsoft.com/download/details.aspx?id=23650>  <br/> |
| <span data-ttu-id="9d11a-747">Windows PowerShell version 3,0</span><span class="sxs-lookup"><span data-stu-id="9d11a-747">Windows Powershell version 3.0</span></span>  <br/>           | <https://www.microsoft.com/download/details.aspx?id=34595>  <br/> |
| <span data-ttu-id="9d11a-748">Visual C++ 2010 Redistributable</span><span class="sxs-lookup"><span data-stu-id="9d11a-748">Visual C++ 2010 Redistributable</span></span>  <br/>          | <https://www.microsoft.com/download/details.aspx?id=5555>  <br/>  |
| <span data-ttu-id="9d11a-749">Mises à jour de Internet Information Server</span><span class="sxs-lookup"><span data-stu-id="9d11a-749">Internet Information Server Updates</span></span>  <br/>      | <https://www.microsoft.com/download/details.aspx?id=34869>  <br/> |
| <span data-ttu-id="9d11a-750">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="9d11a-750">Windows Identity Foundation</span></span>  <br/>              | <https://www.microsoft.com/download/details.aspx?id=17331>  <br/> |
| <span data-ttu-id="9d11a-751">Skype entreprise Server 2015 Setup. exe</span><span class="sxs-lookup"><span data-stu-id="9d11a-751">Skype for Business Server 2015 Setup.exe</span></span>  <br/> | <span data-ttu-id="9d11a-752">Copier à partir du support de Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="9d11a-752">Copy from Skype for Business Server 2015 media</span></span>  <br/>                   |

### <a name="parameter"></a><span data-ttu-id="9d11a-753">Paramètre</span><span class="sxs-lookup"><span data-stu-id="9d11a-753">Parameter</span></span>

<span data-ttu-id="9d11a-754">Le paramètre **-SetupFolder** prend comme argument l’emplacement du répertoire des fichiers prérequis</span><span class="sxs-lookup"><span data-stu-id="9d11a-754">The **-SetupFolder** parameter takes as an argument the directory location of the prerequisite files</span></span>

### <a name="examples"></a><span data-ttu-id="9d11a-755">範例</span><span class="sxs-lookup"><span data-stu-id="9d11a-755">Examples</span></span>

<span data-ttu-id="9d11a-756">Pour exécuter le script SYSPrep. ps1 et installer les composants prérequis de Skype entreprise Server 2015, exécutez la commande suivante à partir d’une invite de commandes avec élévation de privilèges :</span><span class="sxs-lookup"><span data-stu-id="9d11a-756">To run the SYSPrep.ps1 script and install the Skype for Business Server 2015 prerequisites, run the following command from an elevated command prompt:</span></span>

```console
./SysPrep.PS1 -SetupFolder D:\Setup
```

## <a name="unassigned-number-announcements-migration"></a><span data-ttu-id="9d11a-757">Migration des annonces de numéros non attribués</span><span class="sxs-lookup"><span data-stu-id="9d11a-757">Unassigned Number Announcements Migration</span></span>
<span data-ttu-id="9d11a-758"><a name="UNAM"> </a></span><span class="sxs-lookup"><span data-stu-id="9d11a-758"><a name="UNAM"> </a></span></span>

<span data-ttu-id="9d11a-759">L’outil de migration des annonces de numéros non attribués permet à un administrateur Skype entreprise Server 2015 de déplacer la configuration des numéros non attribués qui est desservi par l’application d’annonce à partir d’un serveur ou d’un pool Skype entreprise source vers un destination Skype entreprise Server ou pool.</span><span class="sxs-lookup"><span data-stu-id="9d11a-759">The Unassigned Number Announcements Migration tool enables a Skype for Business Server 2015 administrator to move the unassigned numbers configuration that is serviced by the announcement application from a source Skype for Business Server or Pool to a destination Skype for Business Server or Pool.</span></span>

### <a name="description"></a><span data-ttu-id="9d11a-760">Description</span><span class="sxs-lookup"><span data-stu-id="9d11a-760">Description</span></span>

<span data-ttu-id="9d11a-761">L’outil de migration des annonces de numéros non attribués est un script Windows PowerShell qui déplace la configuration des numéros non attribués Serviced par l’application d’annonce d’un serveur source ou d’un pool vers un autre serveur ou pool.</span><span class="sxs-lookup"><span data-stu-id="9d11a-761">The Unassigned Number Announcements Migration tool is a Windows PowerShell script that moves the unassigned numbers configuration serviced by the announcement application of a source server or pool to a different server or pool.</span></span>

<span data-ttu-id="9d11a-762">Lorsqu’il est exécuté, le script de migration des annonces de numéros non attribués effectue les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="9d11a-762">When executed, the Unassigned Number Announcements Migration script will perform the following operations:</span></span>

1. <span data-ttu-id="9d11a-763">Déplacez tous les fichiers audio utilisés par les annonces de numéros non attribués de l’application d’annonce hébergée dans le serveur ou le pool source vers le magasin de fichiers du serveur ou du pool de destination.</span><span class="sxs-lookup"><span data-stu-id="9d11a-763">Move all the audio files used by the unassigned number announcements of the announcement application hosted in the source server or pool to the file store of the destination server or pool.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9d11a-764">Les fichiers audio sont supprimés du pool source une fois qu’ils sont copiés dans le pool de destination.</span><span class="sxs-lookup"><span data-stu-id="9d11a-764">The audio files are removed from the source pool once they're copied to the destination pool.</span></span>

2. <span data-ttu-id="9d11a-765">Déplacez toutes les annonces de numéros non attribués configurées pour l’application d’annonce hébergée dans le serveur ou le pool source vers le serveur ou le pool de destination.</span><span class="sxs-lookup"><span data-stu-id="9d11a-765">Move all unassigned number announcements configured for the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

3. <span data-ttu-id="9d11a-766">Réaffectez toutes les plages de numéros non attribués qui sont desservies par l’application d’annonce hébergée dans le serveur ou le pool source au serveur ou au pool de destination.</span><span class="sxs-lookup"><span data-stu-id="9d11a-766">Reassign all the unassigned number ranges that are serviced by the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

<span data-ttu-id="9d11a-767">Une fois le script exécuté correctement, toutes les plages de numéros non attribués qui ont été gérées par l’application d’annonce hébergée dans le serveur ou le pool source seront désormais gérées avec la même configuration par le serveur ou le pool de destination.</span><span class="sxs-lookup"><span data-stu-id="9d11a-767">After successfully running the script, all the unassigned number ranges that were serviced by the announcement application hosted in the source server or pool will now be serviced with the same configuration by the destination server or pool.</span></span>

### <a name="output"></a><span data-ttu-id="9d11a-768">Output</span><span class="sxs-lookup"><span data-stu-id="9d11a-768">Output</span></span>

<span data-ttu-id="9d11a-769">Le script **Move-CsAnnouncementConfiguration** indique dans la fenêtre Skype entreprise Server Management Shell où il est exécuté la réussite ou l’échec de l’opération de migration.</span><span class="sxs-lookup"><span data-stu-id="9d11a-769">The **Move-CsAnnouncementConfiguration** script indicates in the Skype for Business Server Management Shell window from where it's executed the success or failure of the migration operation.</span></span>

<span data-ttu-id="9d11a-770">Si l’exécution de l’opération est interrompue par une erreur, les plages de numéros non attribués qui ont été déplacées vers la destination resteront dans la destination sous une forme opérationnelle et le reste des plages de numéros non attribués à migrer restera dans source également dans un formulaire opérationnel.</span><span class="sxs-lookup"><span data-stu-id="9d11a-770">If the execution of the operation is interrupted by any error, the unassigned number ranges that were successfully moved to the destination will remain in the destination in an operational form and the rest of the unassigned number ranges to be migrated will remain in the source as well in an operational form.</span></span> <span data-ttu-id="9d11a-771">Pour effectuer une migration complète du reste de la configuration, réexécutez le script après avoir remédié à l’erreur.</span><span class="sxs-lookup"><span data-stu-id="9d11a-771">To fully migrate the rest of the configuration, rerun the script after addressing the error.</span></span>

### <a name="purpose"></a><span data-ttu-id="9d11a-772">Objectif</span><span class="sxs-lookup"><span data-stu-id="9d11a-772">Purpose</span></span>

<span data-ttu-id="9d11a-773">Le script de migration des annonces de numéros non attribués peut être utilisé dans les trois scénarios suivants :</span><span class="sxs-lookup"><span data-stu-id="9d11a-773">The Unassigned Number Announcements Migration script can be used in the following three scenarios:</span></span>

- <span data-ttu-id="9d11a-774">**Migration des paramètres de configuration vers une nouvelle version de Skype entreprise Server :** Contoso est en train de migrer vers Skype entreprise Server 2015 et, dans le cadre du processus de migration, l’administrateur de Skype entreprise Server souhaite déplacer la configuration des numéros non attribués Serviced par l’application d’annonce depuis le déploiement de Lync Server 2013 vers le nouveau déploiement de Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9d11a-774">**Migrating configuration settings to a new version of Skype for Business Server:** Contoso is in the process of migrating to Skype for Business Server 2015 and as part of the migration process the Skype for Business Server administrator would like to move the unassigned numbers configuration serviced by the announcement application from the Lync Server 2013 deployment to the new Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="9d11a-775">Pour déplacer les paramètres de configuration, l’administrateur de Skype entreprise Server utilise l’outil de migration annonces de numéros non attribués.</span><span class="sxs-lookup"><span data-stu-id="9d11a-775">To move the configuration settings, the Skype for Business Server administrator uses the Unassigned Number Announcements Migration tool.</span></span>

- <span data-ttu-id="9d11a-776">**Restauration d’un déploiement de Skype entreprise Server 2015 vers Lync server 2013 :** En raison de facteurs inattendus, contoso doit restaurer la migration vers le nouveau déploiement de Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9d11a-776">**Rolling back a deployment from Skype for Business Server 2015 to Lync Server 2013:** Due unexpected factors, Contoso has to roll back the migration to the new Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="9d11a-777">Pour minimiser les interruptions du service, l’administrateur de Skype entreprise Server utilise l’outil de migration annonces de numéros non attribués pour restaurer la configuration du déploiement de Skype entreprise Server 2015 vers le déploiement Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9d11a-777">To minimize disruptions to the service, the Skype for Business Server administrator uses the Unassigned Number Announcements Migration tool to roll back the configuration from the Skype for Business Server 2015 deployment to the Lync Server 2013 deployment.</span></span>

- <span data-ttu-id="9d11a-778">**Transfert de données entre les déploiements :** Contoso est en train de remplacer tous les serveurs d’un pool par des serveurs plus récents.</span><span class="sxs-lookup"><span data-stu-id="9d11a-778">**Moving data between deployments:** Contoso is in the process of replacing all the servers of one pool with newer servers.</span></span> <span data-ttu-id="9d11a-779">Leur stratégie est de déployer un nouveau pool Skype entreprise Server 2015, de déplacer toutes les données de l’ancien vers le nouveau, puis de désactiver l’ancien pool.</span><span class="sxs-lookup"><span data-stu-id="9d11a-779">Their strategy is to deploy a new Skype for Business Server 2015 pool, move all the data from the old to the new pool, and then deprecate the old pool.</span></span> <span data-ttu-id="9d11a-780">Une fois le nouveau pool déployé, l’outil de migration annonces de numéros non attribués est utilisé pour déplacer la configuration de l’ancien pool vers le nouveau.</span><span class="sxs-lookup"><span data-stu-id="9d11a-780">Once the new pool is deployed, the Unassigned Number Announcements Migration tool is used to move the configuration from the old pool to the new one.</span></span>

#### <a name="requirements"></a><span data-ttu-id="9d11a-781">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="9d11a-781">Requirements</span></span>

<span data-ttu-id="9d11a-782">Les conditions principales requises pour exécuter correctement l’outil sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="9d11a-782">The following are the main requirements needed to successfully run the tool:</span></span>

1. <span data-ttu-id="9d11a-783">Le script doit être exécuté à partir d’un ordinateur sur lequel Skype entreprise Server Management Shell est installé.</span><span class="sxs-lookup"><span data-stu-id="9d11a-783">The script must be run from a computer that has Skype for Business Server Management Shell installed.</span></span>

2. <span data-ttu-id="9d11a-784">L’application d’annonce doit être déployée avec succès dans les pools ou serveurs Skype entreprise source et destination.</span><span class="sxs-lookup"><span data-stu-id="9d11a-784">The announcement application has to be successfully deployed in the source and destination Skype for Business Servers or Pools.</span></span>

#### <a name="move-csannouncementconfiguration-script"></a><span data-ttu-id="9d11a-785">Script Move-CsAnnouncementConfiguration</span><span class="sxs-lookup"><span data-stu-id="9d11a-785">Move-CsAnnouncementConfiguration script</span></span>

<span data-ttu-id="9d11a-786">Le script Move-CsAnnouncementConfiguration nécessite les deux paramètres décrits dans le tableau ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="9d11a-786">The Move-CsAnnouncementConfiguration script requires the two parameters that are described in the table below.</span></span>

![Paramètres Move-CsAnnouncementConfiguration.](../media/Reskit_2012_Tools_Documentation_Image41.JPG)

### <a name="examples"></a><span data-ttu-id="9d11a-788">範例</span><span class="sxs-lookup"><span data-stu-id="9d11a-788">Examples</span></span>

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-skype-for-business-server-2015-pool"></a><span data-ttu-id="9d11a-789">Transfert de la configuration des annonces de numéros non attribués à partir d’un pool Lync Server 2013 vers un pool Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="9d11a-789">Moving the Unassigned Number Announcements Configuration from a Lync Server 2013 Pool to a Skype for Business Server 2015 Pool</span></span>

<span data-ttu-id="9d11a-790">Cet exemple montre comment déplacer les annonces de numéros non attribués du pool source (Lync Server 2013) vers le pool de destination (Skype entreprise Server 2015).</span><span class="sxs-lookup"><span data-stu-id="9d11a-790">This example moves the unassigned number announcements from the source pool (Lync Server 2013) to the destination pool (Skype for Business Server 2015).</span></span>

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination SfBS2015Pool.contoso.com
```

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-skype-for-business-server-2015-pool-to-a-lync-server-2013-pool"></a><span data-ttu-id="9d11a-791">Transfert de la configuration des annonces de numéros non attribués à partir d’un pool Skype entreprise Server 2015 vers un pool Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9d11a-791">Moving the Unassigned Number Announcements Configuration from a Skype for Business Server 2015 Pool to a Lync Server 2013 Pool</span></span>

<span data-ttu-id="9d11a-792">Cet exemple montre comment déplacer les annonces de numéros non attribués du pool source (Skype entreprise Server 2015) vers le pool de destination (Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="9d11a-792">This example moves the unassigned number announcements from the source pool (Skype for Business Server 2015) to the destination pool (Lync Server 2013).</span></span>

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source SfBS2015Pool.contoso.com -Destination LS2013Pool.contoso.com
```

## <a name="web-conf-data"></a><span data-ttu-id="9d11a-793">Données Web CONF</span><span class="sxs-lookup"><span data-stu-id="9d11a-793">Web Conf Data</span></span>
<span data-ttu-id="9d11a-794"><a name="WebConfData"> </a></span><span class="sxs-lookup"><span data-stu-id="9d11a-794"><a name="WebConfData"> </a></span></span>

<span data-ttu-id="9d11a-795">L’outil Web conf Data permet à un administrateur du logiciel de communications Skype entreprise Server 2015 de contrôler davantage les données associées aux conférences Web d’un organisateur.</span><span class="sxs-lookup"><span data-stu-id="9d11a-795">The Web Conf Data Tool allows an administrator of Skype for Business Server 2015 communications software to have more control over the data associated with an organizer's Web conferences.</span></span> <span data-ttu-id="9d11a-796">Les scénarios incluent la possibilité de supprimer les données de réunion d’un utilisateur spécifique en fonction de critères de date et d’heure.</span><span class="sxs-lookup"><span data-stu-id="9d11a-796">Scenarios include the ability to delete a specific user's meeting data based on a time stamp criteria.</span></span>

### <a name="description"></a><span data-ttu-id="9d11a-797">Description</span><span class="sxs-lookup"><span data-stu-id="9d11a-797">Description</span></span>

<span data-ttu-id="9d11a-798">Cet outil permet à l’administrateur d’effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="9d11a-798">This tool allows the administrator to perform the following operations:</span></span>

1. <span data-ttu-id="9d11a-799">Rechercher toutes les données de conférence Web associées à un utilisateur unique.</span><span class="sxs-lookup"><span data-stu-id="9d11a-799">Find all Web conferencing data associated with a single user.</span></span>

2. <span data-ttu-id="9d11a-800">Supprimer toutes les données de conférence Web associées à un utilisateur unique.</span><span class="sxs-lookup"><span data-stu-id="9d11a-800">Delete all Web conferencing data associated with a single user.</span></span>

3. <span data-ttu-id="9d11a-801">Supprimer toutes les données de conférence Web associées à un seul utilisateur antérieur à une date donnée.</span><span class="sxs-lookup"><span data-stu-id="9d11a-801">Delete all Web conferencing data associated with a single user that is older than a certain date.</span></span>

4. <span data-ttu-id="9d11a-802">Déplacer toutes les données de conférence Web associées à un seul utilisateur lorsque cet utilisateur est déplacé d’un pool vers un autre.</span><span class="sxs-lookup"><span data-stu-id="9d11a-802">Move all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9d11a-803">Les outils du kit de ressources pour Lync Server 2010 prennent en charge le déplacement de toutes les données de conférence Web associées à un utilisateur lorsque celui-ci est déplacé d’un pool vers un autre.</span><span class="sxs-lookup"><span data-stu-id="9d11a-803">The Resource Kit Tools for Lync Server 2010 supported moving all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span> <span data-ttu-id="9d11a-804">Cette fonctionnalité est désormais déconseillée de cet outil en faveur du paramètre **MoveConferenceData** .</span><span class="sxs-lookup"><span data-stu-id="9d11a-804">That functionality is now deprecated from this tool in favor of the **MoveConferenceData** parameter.</span></span> <span data-ttu-id="9d11a-805">Pour plus d’informations sur ce paramètre, voir la cmdlet [Move-Csuser](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="9d11a-805">For details about this parameter, see the [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps) cmdlet.</span></span>

<span data-ttu-id="9d11a-806">L’outil supprime les données de réunion uniquement pour les réunions inactives.</span><span class="sxs-lookup"><span data-stu-id="9d11a-806">The tool deletes meeting data only for meetings that are inactive.</span></span> <span data-ttu-id="9d11a-807">Les réunions actives (ou les réunions en session) ne peuvent pas être supprimées.</span><span class="sxs-lookup"><span data-stu-id="9d11a-807">Active meetings (or meetings in sessions) cannot be deleted.</span></span>

<span data-ttu-id="9d11a-808">Cet outil doit être exécuté à partir d’un ordinateur qui se trouve dans le même pool que l’utilisateur cible.</span><span class="sxs-lookup"><span data-stu-id="9d11a-808">This tool must be run from a computer that is in the same pool as the target user.</span></span> <span data-ttu-id="9d11a-809">L’utilisateur dont les données de contenu de réunion sont gérées par cet outil doit être hébergé dans le même pool d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="9d11a-809">The user whose meeting content data is being managed by this tool must be homed in the same user pool.</span></span>

### <a name="output"></a><span data-ttu-id="9d11a-810">Output</span><span class="sxs-lookup"><span data-stu-id="9d11a-810">Output</span></span>

<span data-ttu-id="9d11a-811">Cet outil renvoie les résultats de chacune des opérations :</span><span class="sxs-lookup"><span data-stu-id="9d11a-811">This tool outputs the results of each of the operations:</span></span>

- <span data-ttu-id="9d11a-812">Si une requête est exécutée, l’outil génère la liste de tous les dossiers de données de réunion inactifs qui ont cet utilisateur comme organisateur.</span><span class="sxs-lookup"><span data-stu-id="9d11a-812">If a query is performed, the tool outputs the list of all inactive meeting data folders that have that user as an organizer.</span></span>

- <span data-ttu-id="9d11a-813">Si une suppression est effectuée, l’outil génère la liste de tous les dossiers de données de réunion dont les données seront supprimées.</span><span class="sxs-lookup"><span data-stu-id="9d11a-813">If a delete is performed, the tool outputs the list of all meeting data folders whose data will be deleted.</span></span>

### <a name="requirements"></a><span data-ttu-id="9d11a-814">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="9d11a-814">Requirements</span></span>

<span data-ttu-id="9d11a-815">L’outil doit être exécuté dans le même pool que l’organisateur.</span><span class="sxs-lookup"><span data-stu-id="9d11a-815">The tool needs to be run in the same pool where the organizer is currently homed.</span></span>

<span data-ttu-id="9d11a-816">L’outil doit être exécuté en utilisant les privilèges d’administrateur pour accéder au magasin de fichiers de contenu.</span><span class="sxs-lookup"><span data-stu-id="9d11a-816">The tool must be run using administrator privileges with access to the Content File Store.</span></span>

### <a name="examples"></a><span data-ttu-id="9d11a-817">範例</span><span class="sxs-lookup"><span data-stu-id="9d11a-817">Examples</span></span>

<span data-ttu-id="9d11a-818">Le tableau suivant décrit les paramètres, dont certains sont utilisés dans les exemples.</span><span class="sxs-lookup"><span data-stu-id="9d11a-818">The following table describes the parameters, some of which are used in the examples.</span></span>

![Paramètres de l’outil Web conf Data.](../media/Reskit_2012_Tools_Documentation_Image51.JPG)

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""
```

<span data-ttu-id="9d11a-820">L’exemple précédent illustre le fonctionnement d’une commande de requête.</span><span class="sxs-lookup"><span data-stu-id="9d11a-820">The preceding example shows how a query command would work.</span></span> <span data-ttu-id="9d11a-821">La sortie de cette commande serait une liste de tous les dossiers de contenu de réunion qui seraient affectés par cet outil.</span><span class="sxs-lookup"><span data-stu-id="9d11a-821">The output of such a command would be a list of all meeting content folders that would be affected by this tool.</span></span>

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:delete
```

<span data-ttu-id="9d11a-822">Le précédent est un exemple de commande Delete.</span><span class="sxs-lookup"><span data-stu-id="9d11a-822">The preceding is an example of a delete command.</span></span> <span data-ttu-id="9d11a-823">La commande Supprimer supprime tous les dossiers de réunion inactifs de cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9d11a-823">The delete command will remove all inactive meeting folders from this user.</span></span>

### <a name="summary"></a><span data-ttu-id="9d11a-824">Résumé</span><span class="sxs-lookup"><span data-stu-id="9d11a-824">Summary</span></span>

<span data-ttu-id="9d11a-825">Cet outil peut être une ressource précieuse pour les administrateurs qui ont besoin d’un contrôle plus précis sur les données de réunion de conférence.</span><span class="sxs-lookup"><span data-stu-id="9d11a-825">This tool can be a valuable resource to administrators who need more precise control over conference meeting data.</span></span>


