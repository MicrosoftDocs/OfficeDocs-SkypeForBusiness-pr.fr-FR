---
title: Documentation sur les outils du kit de ressources Lync Server 2013
description: Documentation sur les outils du kit de ressources Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Resource Kit Tools Documentation
ms:assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945604(v=OCS.15)
ms:contentKeyID: 51541429
ms.date: 02/02/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6866e04615014daa7e93f7e7f1081b10325d087d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573560"
---
# <a name="lync-server-2013-resource-kit-tools-documentation"></a><span data-ttu-id="a719c-103">Documentation sur les outils du kit de ressources Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a719c-103">Lync Server 2013 Resource Kit Tools Documentation</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a719c-104">_**Dernière modification de la rubrique :** 2014-01-09_</span><span class="sxs-lookup"><span data-stu-id="a719c-104">_**Topic Last Modified:** 2014-01-09_</span></span>

<span data-ttu-id="a719c-105">Cette rubrique décrit les outils qui font partie du kit de ressources Lync Server 2013, y compris l’objectif de chaque outil, ainsi que des exemples de son utilisation. Les outils du kit de ressources Lync Server 2013 facilitent les tâches de routine pour les administrateurs qui déploient et gèrent Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a719c-105">This topic describes the tools that are part of the Lync Server 2013 Resource Kit, including the purpose of each tool, and examples of its use.The Lync Server 2013, Resource Kit Tools help to make routine tasks easier for IT administrators who deploy and manage Lync Server 2013.</span></span> <span data-ttu-id="a719c-106">Par exemple, l’outil **Web conf Data** peut être utilisé pour contrôler facilement les données téléchargées par les utilisateurs au cours d’une réunion en ligne.</span><span class="sxs-lookup"><span data-stu-id="a719c-106">For example, the **Web Conf Data** tool can be used to easily control data that is uploaded by users during an online meeting.</span></span> <span data-ttu-id="a719c-107">L’outil **SEFAUtil** peut être utilisé pour configurer le transfert d’appel de délégué et la réponse pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a719c-107">The **SEFAUtil** tool can be used to set up delegate call forwarding and answering for users.</span></span> <span data-ttu-id="a719c-108">Nous encourageons les administrateurs informatiques à utiliser ces outils pour gérer plus efficacement Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a719c-108">We encourage IT administrators to use these tools to more effectively manage Lync Server 2013.</span></span>

<div>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="a719c-109">Installation des outils du kit de ressources</span><span class="sxs-lookup"><span data-stu-id="a719c-109">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="a719c-110">Pour installer les outils du kit de ressources Lync Server 2013, téléchargez **OCSReskit.msi**.</span><span class="sxs-lookup"><span data-stu-id="a719c-110">To install the Lync Server 2013, Resource Kit Tools, download **OCSReskit.msi**.</span></span> <span data-ttu-id="a719c-111">Vous pouvez télécharger le programme d’installation des outils du kit de ressources à partir du centre de téléchargement à l’adresse [https://go.microsoft.com/fwlink/p/?LinkID=330429](https://go.microsoft.com/fwlink/p/?linkid=330429) .</span><span class="sxs-lookup"><span data-stu-id="a719c-111">You can download the Resource Kit Tools installer from the Download Center at [https://go.microsoft.com/fwlink/p/?LinkID=330429](https://go.microsoft.com/fwlink/p/?linkid=330429).</span></span>

<span data-ttu-id="a719c-112">Exécutez **OCSResKit.msi** pour effectuer une installation simple.</span><span class="sxs-lookup"><span data-stu-id="a719c-112">Run **OCSResKit.msi** to do a simple installation.</span></span> <span data-ttu-id="a719c-113">Le fichier. msi installe tous les outils dans le chemin d’accès suivant : **% Program Files% \\ Microsoft Lync Server 2013 \\ reskit**.</span><span class="sxs-lookup"><span data-stu-id="a719c-113">The .msi installs all the tools in the following path: **%Program Files%\\Microsoft Lync Server 2013\\ResKit**.</span></span> <span data-ttu-id="a719c-114">Les outils qui sont des fichiers exécutables autonomes se trouvent dans ce dossier.</span><span class="sxs-lookup"><span data-stu-id="a719c-114">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="a719c-115">Les outils qui ont également des fichiers se trouvent dans leurs propres sous-dossiers.</span><span class="sxs-lookup"><span data-stu-id="a719c-115">Tools that also have files are in their own subfolders.</span></span>

</div>

<div>

## <a name="supported-environments"></a><span data-ttu-id="a719c-116">Environnements pris en charge</span><span class="sxs-lookup"><span data-stu-id="a719c-116">Supported Environments</span></span>

<span data-ttu-id="a719c-117">Pour des performances optimales, les outils du kit de ressources Lync Server 2013 doivent être installés dans le même environnement et avec les mêmes spécifications que celles requises pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a719c-117">For optimal performance, the Lync Server 2013, Resource Kit Tools should be installed in the same environment and with the same specifications that are required for Lync Server 2013.</span></span>

</div>

<div>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="a719c-118">Vue d’ensemble des outils du kit de ressources</span><span class="sxs-lookup"><span data-stu-id="a719c-118">Resource Kit Tools Overview</span></span>

<span data-ttu-id="a719c-119">La liste suivante décrit les outils fournis dans le kit de ressources de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a719c-119">The following list describes the tools that are provided in the Lync Server 2013 Resource Kit.</span></span> <span data-ttu-id="a719c-120">Une description de chaque outil, notamment les conditions requises et l’utilisation de l’exemple, est décrite dans la section suivante.</span><span class="sxs-lookup"><span data-stu-id="a719c-120">A description of each tool, including the requirements and example usage is covered in the following section.</span></span>

  - <span data-ttu-id="a719c-121">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="a719c-121">ABSConfig</span></span>

  - <span data-ttu-id="a719c-122">Moniteur de service de stratégie de bande passante</span><span class="sxs-lookup"><span data-stu-id="a719c-122">Bandwidth Policy Service Monitor</span></span>

  - <span data-ttu-id="a719c-123">Analyseur d’utilisation de la bande passante</span><span class="sxs-lookup"><span data-stu-id="a719c-123">Bandwidth Utilization Analyzer</span></span>

  - <span data-ttu-id="a719c-124">Appeler Parkometer</span><span class="sxs-lookup"><span data-stu-id="a719c-124">Call Parkometer</span></span>

  - <span data-ttu-id="a719c-125">CleanupStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="a719c-125">CleanupStorageServiceData</span></span>

  - <span data-ttu-id="a719c-126">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="a719c-126">DBAnalyze</span></span>

  - <span data-ttu-id="a719c-127">ImportStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="a719c-127">ImportStorageServiceData</span></span>

  - <span data-ttu-id="a719c-128">LCSSync</span><span class="sxs-lookup"><span data-stu-id="a719c-128">LCSSync</span></span>

  - <span data-ttu-id="a719c-129">LookupUserConsole</span><span class="sxs-lookup"><span data-stu-id="a719c-129">LookupUserConsole</span></span>

  - <span data-ttu-id="a719c-130">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="a719c-130">MsTurnPing</span></span>

  - <span data-ttu-id="a719c-131">Afficheur de configuration réseau</span><span class="sxs-lookup"><span data-stu-id="a719c-131">Network Configuration Viewer</span></span>

  - <span data-ttu-id="a719c-132">Response Group agent Live</span><span class="sxs-lookup"><span data-stu-id="a719c-132">Response Group Agent Live</span></span>

  - <span data-ttu-id="a719c-133">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="a719c-133">SEFAUtil</span></span>

  - <span data-ttu-id="a719c-134">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="a719c-134">SYSPrep.ps1</span></span>

  - <span data-ttu-id="a719c-135">Migration des annonces de numéros non attribués</span><span class="sxs-lookup"><span data-stu-id="a719c-135">Unassigned Number Announcements Migration</span></span>

  - <span data-ttu-id="a719c-136">Données Web CONF</span><span class="sxs-lookup"><span data-stu-id="a719c-136">Web Conf Data</span></span>

</div>

<div>

## <a name="absconfig"></a><span data-ttu-id="a719c-137">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="a719c-137">ABSConfig</span></span>

<span data-ttu-id="a719c-138">L’outil de configuration du service de carnet d’adresses (ABSConfig) est un outil d’administration qui permet aux administrateurs de personnaliser la configuration du service de carnet d’adresses dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a719c-138">The Address Book Service Configuration tool (ABSConfig) is an administrative tool that helps administrators customize Address Book Service configuration in Lync Server 2013.</span></span> <span data-ttu-id="a719c-139">Cet outil permet également aux administrateurs Lync Server 2013 de restaurer les paramètres par défaut du service de carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="a719c-139">This tool also enables Lync Server 2013 administrators to restore the default Address Book Service settings.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="a719c-140">Description</span><span class="sxs-lookup"><span data-stu-id="a719c-140">Description</span></span>

<span data-ttu-id="a719c-141">ABSConfig est une application d’interface utilisateur graphique qui permet aux administrateurs de configurer les attributs des services de domaine Active Directory associés au service de carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="a719c-141">ABSConfig is a graphical user interface application that enables administrators to configure Active Directory Domain Services attributes that are related to Address Book Service.</span></span>

<span data-ttu-id="a719c-142">Les principaux scénarios de l’outil sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="a719c-142">The primary scenarios for the tool are the following:</span></span>

  - <span data-ttu-id="a719c-143">Permettre aux administrateurs de mapper les attributs des services de domaine Active Directory aux attributs de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a719c-143">To enable administrators to map attributes in Active Directory Domain Services to the attributes for Lync Server 2013.</span></span>

  - <span data-ttu-id="a719c-144">Pour permettre aux administrateurs de spécifier l’attribut des services de domaine Active Directory à inclure ou exclure dans les fichiers du service de carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="a719c-144">To enable administrators to specify the Active Directory Domain Services attribute to be included or excluded in the Address Book Service files.</span></span>

  - <span data-ttu-id="a719c-145">Pour permettre aux administrateurs de restaurer les paramètres par défaut du service de carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="a719c-145">To enable administrators to restore default Address Book Service settings.</span></span>

<span data-ttu-id="a719c-146">L’outil ABSConfig peut être démarré à l’aide du fichier absConfig.exe.</span><span class="sxs-lookup"><span data-stu-id="a719c-146">The ABSConfig tool can be started by using the absConfig.exe file.</span></span> <span data-ttu-id="a719c-147">L’outil s’ouvre sur l’onglet **configurer les attributs** . Ce tableau comporte des options permettant de mapper les attributs des services de domaine Active Directory avec les champs d’attribut de Lync Server 2013 et de spécifier les utilisateurs à inclure ou à exclure dans les fichiers du service de carnet d’adresses en fonction de filtres d’attributs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="a719c-147">The tool opens to the **Configure Attributes** tab. This table has options to map Active Directory Domain Services attributes to the attribute fields for Lync Server 2013 and to specify which users to include or exclude in Address Book Service files based on specific attribute filters.</span></span> <span data-ttu-id="a719c-148">Elle comporte également des options permettant de personnaliser la valeur du numéro de téléphone à inclure dans le fichier de carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="a719c-148">It also has options to customize which value of the phone number to be included in the Address Book file.</span></span> <span data-ttu-id="a719c-149">L’option restaurer les paramètres **par défaut** permet aux administrateurs de restaurer les valeurs par défaut des paramètres du service de carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="a719c-149">The **Restore Defaults** option enables administrators to restore Address Book Service settings to default values.</span></span>

</div>

<div>

## <a name="changes-from-lync-server-2010"></a><span data-ttu-id="a719c-150">Modifications à partir de Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="a719c-150">Changes from Lync Server 2010</span></span>

<span data-ttu-id="a719c-151">Dans l’outil de configuration ABS de Lync Server 2013, les attributs (lignes) peuvent être supprimés en désactivant la case à cocher « Activer » pour l’attribut.</span><span class="sxs-lookup"><span data-stu-id="a719c-151">In Lync Server 2013 ABS Configuration tool, attributes (rows) may be removed by unchecking the “enable” checkbox for the attribute.</span></span> <span data-ttu-id="a719c-152">Cela équivaut à supprimer la ligne dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a719c-152">This has the same effect as deleting the row in Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a719c-153">La case à cocher Activer se trouve dans la colonne la plus à droite ; vous devrez peut-être faire défiler la liste vers la droite pour voir la colonne</span><span class="sxs-lookup"><span data-stu-id="a719c-153">The enable checkbox is in the far right column; you may need to scroll right to see the column</span></span>



</div>

</div>

<div>

## <a name="output"></a><span data-ttu-id="a719c-154">Output</span><span class="sxs-lookup"><span data-stu-id="a719c-154">Output</span></span>

<span data-ttu-id="a719c-155">ABSConfig stocke la configuration du service de carnet d’adresses dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="a719c-155">ABSConfig stores the Address Book Service configuration in the database.</span></span>

    Path: %ProgramFiles%\Microsoft Lync Server 2013\Reskit

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="a719c-156">Objectif</span><span class="sxs-lookup"><span data-stu-id="a719c-156">Purpose</span></span>

<span data-ttu-id="a719c-157">ABSConfig offre un moyen rapide et simple de personnaliser le service de carnet d’adresses Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a719c-157">ABSConfig provides a quick and easy way to customize Lync Server 2013 Address Book Service.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="a719c-158">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="a719c-158">Requirements</span></span>

<div>

## <a name="computer"></a><span data-ttu-id="a719c-159">Ordinateur</span><span class="sxs-lookup"><span data-stu-id="a719c-159">Computer</span></span>

<span data-ttu-id="a719c-160">ABSConfig ne peut être exécuté qu’à partir d’un ordinateur joint à un domaine sur lequel Lync Server 2013 est installé.</span><span class="sxs-lookup"><span data-stu-id="a719c-160">ABSConfig can be run only from a domain-joined computer that has Lync Server 2013 installed.</span></span> <span data-ttu-id="a719c-161">Dans le cas de Lync Server 2013, Enterprise Edition, cet outil peut être exécuté sur tous les serveurs frontaux pour lesquels le service de carnet d’adresses est activé lors de l’installation.</span><span class="sxs-lookup"><span data-stu-id="a719c-161">In the case of Lync Server 2013, Enterprise Edition, this tool can be run on any Front End servers that have the Address Book Service enabled during setup.</span></span>

</div>

<div>

## <a name="network"></a><span data-ttu-id="a719c-162">Réseau</span><span class="sxs-lookup"><span data-stu-id="a719c-162">Network</span></span>

<span data-ttu-id="a719c-163">L’ordinateur doit être en mesure de se connecter au pool frontal et à la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="a719c-163">The computer should be able to connect to the Front End pool and back-end database.</span></span>

</div>

<div>

## <a name="software"></a><span data-ttu-id="a719c-164">Logiciels</span><span class="sxs-lookup"><span data-stu-id="a719c-164">Software</span></span>

<span data-ttu-id="a719c-165">Les composants logiciels suivants doivent être installés avant d’exécuter l’outil ABSConfig :</span><span class="sxs-lookup"><span data-stu-id="a719c-165">The following software components must be installed before running the ABSConfig tool:</span></span>

  - <span data-ttu-id="a719c-166">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a719c-166">Microsoft Lync Server 2013</span></span>

</div>

<div>

## <a name="users"></a><span data-ttu-id="a719c-167">Utilisateurs</span><span class="sxs-lookup"><span data-stu-id="a719c-167">Users</span></span>

<span data-ttu-id="a719c-168">Administrateurs disposant des autorisations nécessaires pour mettre à jour le déploiement de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a719c-168">Administrators who have the permissions required to update the Lync Server 2013 deployment.</span></span>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="a719c-169">Exemples</span><span class="sxs-lookup"><span data-stu-id="a719c-169">Examples</span></span>

<span data-ttu-id="a719c-170">ABSConfig peut être démarré en tapant **ABSConfig.exe** à une invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="a719c-170">ABSConfig can be started by typing **ABSConfig.exe** at a command prompt.</span></span> <span data-ttu-id="a719c-171">L’interface utilisateur de l’outil ABSConfig est illustrée ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="a719c-171">Shown below is the ABSConfig tool user interface.</span></span>

<span data-ttu-id="a719c-172">![Outil ABSConfig.exe.](images/JJ945604.6fb63a70-7b63-4b8b-b7d1-82fe9aa2028f(OCS.15).jpg "Outil ABSConfig.exe.")</span><span class="sxs-lookup"><span data-stu-id="a719c-172">![The ABSConfig.exe tool.](images/JJ945604.6fb63a70-7b63-4b8b-b7d1-82fe9aa2028f(OCS.15).jpg "The ABSConfig.exe tool.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="a719c-173">Résumé</span><span class="sxs-lookup"><span data-stu-id="a719c-173">Summary</span></span>

<span data-ttu-id="a719c-174">L’outil ABSConfig fournit aux administrateurs un outil rapide et facile à utiliser pour personnaliser le service de carnet d’adresses Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a719c-174">The ABSConfig tool provides administrators a quick and easy to use tool to customize Lync Server 2013 Address Book Service.</span></span>

</div>

</div>

<div>

## <a name="bandwidth-policy-service-monitor"></a><span data-ttu-id="a719c-175">Moniteur de service de stratégie de bande passante</span><span class="sxs-lookup"><span data-stu-id="a719c-175">Bandwidth Policy Service Monitor</span></span>

<span data-ttu-id="a719c-176">L’outil Moniteur de service de stratégie de bande passante permet aux administrateurs d’afficher la liste des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="a719c-176">The Bandwidth Policy Service Monitor tool is intended to allow administrators to view a list of the following:</span></span>

1.  <span data-ttu-id="a719c-177">Tous les services de stratégie de bande passante Lync Server 2013 configurés (authentification et cœur) dans la topologie</span><span class="sxs-lookup"><span data-stu-id="a719c-177">All the configured Lync Server 2013 Bandwidth Policy services (Authentication and Core) in the topology</span></span>

2.  <span data-ttu-id="a719c-178">Les connexions que chaque service effectue à d’autres services de stratégie de bande passante et aux serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="a719c-178">The connections that each service makes to other Bandwidth Policy services and to the Edge servers</span></span>

3.  <span data-ttu-id="a719c-179">Tous les liens configurés dans le document de configuration réseau et l’utilisation de la bande passante en temps réel comme indiqué par chacun des services de stratégie de bande passante</span><span class="sxs-lookup"><span data-stu-id="a719c-179">All the links that are configured in the Network configuration document and real-time bandwidth usage as reported by each of the Bandwidth Policy services</span></span>

<div>

## <a name="description"></a><span data-ttu-id="a719c-180">Description</span><span class="sxs-lookup"><span data-stu-id="a719c-180">Description</span></span>

<span data-ttu-id="a719c-181">L’outil Moniteur de service de stratégie de bande passante est implémenté en tant qu’application basée sur une interface utilisateur graphique.</span><span class="sxs-lookup"><span data-stu-id="a719c-181">The Bandwidth Policy Service Monitor tool is implemented as a GUI-based application.</span></span> <span data-ttu-id="a719c-182">Les administrateurs démarrent l’outil en exécutant PDPMonUI.exe.</span><span class="sxs-lookup"><span data-stu-id="a719c-182">Administrators start the tool by running PDPMonUI.exe.</span></span>

<span data-ttu-id="a719c-183">Lorsque l’outil démarre, il tente de découvrir la liste des services de stratégie de bande passante dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="a719c-183">When the tool starts, it attempts to discover the list of Bandwidth Policy services in the topology.</span></span> <span data-ttu-id="a719c-184">Une fois la mise à jour initiale terminée, le volet à gauche de la fenêtre est renseigné avec une liste de services qui sont regroupés par les clusters auxquels ils appartiennent.</span><span class="sxs-lookup"><span data-stu-id="a719c-184">After the initial update is done, the pane to the left of the window is populated with a list of services that are grouped by the clusters that they belong to.</span></span>

<span data-ttu-id="a719c-185">Lorsque les administrateurs sélectionnent un service de stratégie de bande passante particulier, le volet de droite affiche les informations relatives à ce service particulier.</span><span class="sxs-lookup"><span data-stu-id="a719c-185">When administrators select a particular Bandwidth Policy Service, the pane on the right displays the information about that particular service.</span></span> <span data-ttu-id="a719c-186">Ce volet comporte également deux onglets principaux qui affichent des informations.</span><span class="sxs-lookup"><span data-stu-id="a719c-186">That pane also has two main tabs that display information.</span></span>

<div>

## <a name="machine-info-tab"></a><span data-ttu-id="a719c-187">Onglet Infos ordinateur</span><span class="sxs-lookup"><span data-stu-id="a719c-187">Machine Info Tab</span></span>

<span data-ttu-id="a719c-188">L’onglet **infos ordinateur** affiche les détails du service de stratégie de bande passante sélectionné et la liste et l’état de toutes les connexions établies par le service de stratégie de bande passante sélectionné à d’autres services.</span><span class="sxs-lookup"><span data-stu-id="a719c-188">The **Machine Info** tab shows the details of the Bandwidth Policy Service that is selected and the list and state of all the connections that are made by the selected Bandwidth Policy Service to other services.</span></span>

</div>

<div>

## <a name="topology-info-tab"></a><span data-ttu-id="a719c-189">Onglet informations sur la topologie</span><span class="sxs-lookup"><span data-stu-id="a719c-189">Topology Info Tab</span></span>

<span data-ttu-id="a719c-190">L’onglet **informations sur la topologie** affiche une liste de tous les liens configurés dans les paramètres de configuration du réseau.</span><span class="sxs-lookup"><span data-stu-id="a719c-190">The **Topology Info** tab shows a list of all the links that are configured in the Network configuration settings.</span></span> <span data-ttu-id="a719c-191">Pour chaque lien, la capacité de bande passante audio et vidéo est affichée.</span><span class="sxs-lookup"><span data-stu-id="a719c-191">For each link, the audio and video bandwidth capacity is displayed.</span></span> <span data-ttu-id="a719c-192">En outre, la bande passante actuellement utilisée est affichée, à la fois en Kbits/s et en pourcentage de la capacité.</span><span class="sxs-lookup"><span data-stu-id="a719c-192">Additionally, the currently utilized bandwidth is displayed, both in Kbps and as a percentage of the capacity.</span></span> <span data-ttu-id="a719c-193">L’outil utilise un codage en couleurs pour mettre en surbrillance les liens dont l’utilisation est proche de la capacité, ce qui permet aux administrateurs d’isoler rapidement ces liens.</span><span class="sxs-lookup"><span data-stu-id="a719c-193">The tool uses color-coding to highlight links that have utilization that is close to the capacity—this allows administrators to quickly isolate such links.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a719c-194">Si l’outil Moniteur de service de stratégie de bande passante rencontre une défaillance lorsqu’il se connecte à l’un des services de stratégie de bande passante configurés, les informations des onglets <STRONG>infos ordinateur</STRONG> et informations sur la <STRONG>topologie</STRONG> ne seront pas renseignées.</span><span class="sxs-lookup"><span data-stu-id="a719c-194">If the Bandwidth Policy Service Monitor tool experiences failure when it connects to any of the configured Bandwidth Policy services, the information in the <STRONG>Machine Info</STRONG> and the <STRONG>Topology Info</STRONG> tabs won’t be populated.</span></span> <span data-ttu-id="a719c-195">Toutefois, il est possible que l’outil se connecte à l’origine, mais perd sa connexion au service.</span><span class="sxs-lookup"><span data-stu-id="a719c-195">However, it is possible that the tool might connect initially but subsequently lose its connection to the service.</span></span> <span data-ttu-id="a719c-196">Dans ce cas, les administrateurs peuvent voir des informations périmées.</span><span class="sxs-lookup"><span data-stu-id="a719c-196">In such cases, administrators might see outdated information.</span></span> <span data-ttu-id="a719c-197">Il existe un <STRONG>dernier horodatage mis à jour</STRONG> sur chacun des onglets qui permet aux administrateurs de savoir quand les données ont été mises à jour pour un service de stratégie de bande passante particulier.</span><span class="sxs-lookup"><span data-stu-id="a719c-197">There is a <STRONG>Last Updated</STRONG> time stamp on each of the tabs that can allow administrators to see when the data was last updated for a particular Bandwidth Policy Service.</span></span>



</div>

</div>

</div>

<div>

## <a name="output"></a><span data-ttu-id="a719c-198">Output</span><span class="sxs-lookup"><span data-stu-id="a719c-198">Output</span></span>

<span data-ttu-id="a719c-199">Il n’y a pas de sortie de ligne de commande ; la sortie du programme est contenue dans l’interface utilisateur graphique principale.</span><span class="sxs-lookup"><span data-stu-id="a719c-199">There is no command-line output; the program output is contained within the main graphical user interface (GUI).</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="a719c-200">Objectif</span><span class="sxs-lookup"><span data-stu-id="a719c-200">Purpose</span></span>

<span data-ttu-id="a719c-201">L’objectif de l’outil Moniteur de service de stratégie de bande passante est de permettre aux administrateurs de visualiser l’état de chacun des services de stratégie de bande passante définis dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="a719c-201">The purpose of the Bandwidth Policy Service Monitor tool is to allow administrators visibility into the state of each of the Bandwidth Policy services that are defined in the topology.</span></span> <span data-ttu-id="a719c-202">En outre, les administrateurs peuvent voir l’utilisation de la bande passante en temps réel pour tous les liens définis dans le document de configuration du réseau.</span><span class="sxs-lookup"><span data-stu-id="a719c-202">In addition, administrators can see real-time bandwidth usage for all the links that are defined in the Network configuration document.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="a719c-203">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="a719c-203">Requirements</span></span>

<span data-ttu-id="a719c-204">L’outil Moniteur de service de stratégie de bande passante doit être exécuté sur un ordinateur qui fait partie de la topologie Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a719c-204">The Bandwidth Policy Service Monitor tool needs to be run on a computer that is part of the Lync Server topology.</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="a719c-205">Résumé</span><span class="sxs-lookup"><span data-stu-id="a719c-205">Summary</span></span>

<span data-ttu-id="a719c-206">L’outil Moniteur de service de stratégie de bande passante peut être une ressource intéressante pour les administrateurs afin qu’ils puissent inspecter l’état de tous les services de stratégie de bande passante dans la topologie, et plus important, ils peuvent obtenir une utilisation en temps réel de la bande passante pour les liens définis dans les paramètres de configuration du réseau.</span><span class="sxs-lookup"><span data-stu-id="a719c-206">The Bandwidth Policy Service Monitor tool can be a valuable resource to administrators so they can inspect the state of all the Bandwidth Policy services in the topology—and more importantly—they can obtain real-time bandwidth utilization for the links that are defined in the Network configuration settings.</span></span>

</div>

</div>

<div>

## <a name="bandwidth-utilization-analyzer"></a><span data-ttu-id="a719c-207">Analyseur d’utilisation de la bande passante</span><span class="sxs-lookup"><span data-stu-id="a719c-207">Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="a719c-208">L’analyseur d’utilisation de la bande passante est un outil qui crée des rapports sur les différentes vues de la consommation de bande passante par les points de terminaison UC sur les liaisons de réseau étendu dans le réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="a719c-208">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network.</span></span> <span data-ttu-id="a719c-209">Ces rapports peuvent être utilisés pour comprendre le modèle de consommation de bande passante actuel et pour faciliter la planification de la capacité de bande passante.</span><span class="sxs-lookup"><span data-stu-id="a719c-209">These reports can be used to understand the current bandwidth consumption pattern and to aid in bandwidth capacity planning.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="a719c-210">Description</span><span class="sxs-lookup"><span data-stu-id="a719c-210">Description</span></span>

<span data-ttu-id="a719c-211">L’analyseur d’utilisation de la bande passante est implémenté en tant qu’application basée sur une interface utilisateur graphique.</span><span class="sxs-lookup"><span data-stu-id="a719c-211">Bandwidth Utilization Analyzer is implemented as a GUI-based application.</span></span> <span data-ttu-id="a719c-212">Cet outil génère des rapports spécifiquement pour l’utilisation audio sur le réseau et vous aide à planifier la capacité.</span><span class="sxs-lookup"><span data-stu-id="a719c-212">This tool generates reports specifically for audio utilization across the network and helps with capacity planning.</span></span> <span data-ttu-id="a719c-213">Elle effectue également une itération sur la capacité de bande passante affectée à différents liens.</span><span class="sxs-lookup"><span data-stu-id="a719c-213">It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="a719c-214">Output</span><span class="sxs-lookup"><span data-stu-id="a719c-214">Output</span></span>

<span data-ttu-id="a719c-215">Bandwidth utilization Analyzer fournit des tracés graphiques de la capacité de bande passante et de l’utilisation de l’audio pour toutes les liaisons de réseau étendu configurées dans le système.</span><span class="sxs-lookup"><span data-stu-id="a719c-215">Bandwidth Utilization Analyzer provides graphic al plots of bandwidth capacity and utilization for audio for all the WAN links that are configured in the system.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="a719c-216">Objectif</span><span class="sxs-lookup"><span data-stu-id="a719c-216">Purpose</span></span>

<span data-ttu-id="a719c-217">Dans tout déploiement vocal et vidéo, il est essentiel de surveiller et de comprendre la tendance de l’utilisation de la bande passante du trafic multimédia sur le réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="a719c-217">In any voice and video deployment, it’s critical to monitor and understand the trend of bandwidth utilization of media traffic across the enterprise network.</span></span> <span data-ttu-id="a719c-218">L’outil d’analyse de l’utilisation de la bande passante permet à un administrateur d’atteindre le même objectif.</span><span class="sxs-lookup"><span data-stu-id="a719c-218">The Bandwidth Utilization Analyzer tool allows an administrator to achieve just that.</span></span> <span data-ttu-id="a719c-219">Cet outil effectue les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="a719c-219">This tool does the following:</span></span>

  - <span data-ttu-id="a719c-220">Génère des rapports spécifiques pour l’utilisation audio sur le réseau</span><span class="sxs-lookup"><span data-stu-id="a719c-220">Generates specific reports for audio utilization across the network</span></span>

  - <span data-ttu-id="a719c-221">Permet une planification et une itération de capacité plus efficaces sur la capacité de bande passante affectée à différents liens</span><span class="sxs-lookup"><span data-stu-id="a719c-221">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="a719c-222">Bandwidth utilization Analyzer peut générer des placettes graphiques de capacité de bande passante et de rapports d’utilisation ; Il s’agit des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="a719c-222">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and utilization reports; they are as follows:</span></span>

  - <span data-ttu-id="a719c-223">Toutes les liaisons de réseau étendu dans le réseau d’entreprise</span><span class="sxs-lookup"><span data-stu-id="a719c-223">All the WAN links in the enterprise network</span></span>

  - <span data-ttu-id="a719c-224">Filtré par les liaisons WAN sélectionnées qui ont été choisies</span><span class="sxs-lookup"><span data-stu-id="a719c-224">Filtered by selected WAN links that have been chosen</span></span>

  - <span data-ttu-id="a719c-225">Filtrés par des liaisons de réseau étendu ayant dépassé la capacité de liaison</span><span class="sxs-lookup"><span data-stu-id="a719c-225">Filtered by WAN links that have exceeded link capacity</span></span>

  - <span data-ttu-id="a719c-226">Filtrés par des liaisons de réseau étendu qui ont été sous-utilisant la bande passante approvisionnée</span><span class="sxs-lookup"><span data-stu-id="a719c-226">Filtered by WAN links that have been under-utilizing the provisioned bandwidth</span></span>

  - <span data-ttu-id="a719c-227">Filtrer par les liaisons de réseau étendu qui ont atteint des niveaux critiques (une utilisation de bande passante supérieure à 90% de la capacité de bande passante de la liaison de réseau étendu)</span><span class="sxs-lookup"><span data-stu-id="a719c-227">Filter by WAN links that have been reaching critical levels (a bandwidth utilization that is greater than 90% of bandwidth capacity of the WAN link)</span></span>

  - <span data-ttu-id="a719c-228">Filtré par type de lien WAN — liaisons de sites réseau, liens interrégionaux et liens au sein d’un site</span><span class="sxs-lookup"><span data-stu-id="a719c-228">Filtered by WAN link type—network-site links, interregional links, and links within a site</span></span>

  - <span data-ttu-id="a719c-229">Filtré par région réseau</span><span class="sxs-lookup"><span data-stu-id="a719c-229">Filtered by network region</span></span>

<div>

## <a name="applications"></a><span data-ttu-id="a719c-230">Applications</span><span class="sxs-lookup"><span data-stu-id="a719c-230">Applications</span></span>

<span data-ttu-id="a719c-231">L’analyseur d’utilisation de la bande passante comporte les deux applications suivantes (outils) :</span><span class="sxs-lookup"><span data-stu-id="a719c-231">Bandwidth Utilization Analyzer has the following two applications (tools):</span></span>

  - <span data-ttu-id="a719c-232">**WanLinkLogCollector.exe**     Cet outil permet à son utilisateur d’entrer les informations requises.</span><span class="sxs-lookup"><span data-stu-id="a719c-232">**WanLinkLogCollector.exe**   This tool enables its user to input the required information.</span></span>

  - <span data-ttu-id="a719c-233">**BandwidthUtilizationAnalyzer.xlsm**    Un rapport de logiciel de feuille de calcul Microsoft Excel est automatiquement lancé par WanLinkLogCollector.exe.</span><span class="sxs-lookup"><span data-stu-id="a719c-233">**BandwidthUtilizationAnalyzer.xlsm**  A Microsoft Excel spreadsheet software report is automatically launched by WanLinkLogCollector.exe.</span></span> <span data-ttu-id="a719c-234">Cette application permet à l’utilisateur d’appliquer des filtres au rapport, comme indiqué plus loin dans cet article.</span><span class="sxs-lookup"><span data-stu-id="a719c-234">This application allows the user to apply filters to the report as shown later in this article.</span></span>

</div>

<div>

## <a name="phases-of-using-bandwidth-utilization-analyzer"></a><span data-ttu-id="a719c-235">Phases de l’utilisation de l’analyseur d’utilisation de la bande passante</span><span class="sxs-lookup"><span data-stu-id="a719c-235">Phases of Using Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="a719c-236">Il existe deux phases lors de l’utilisation de l’analyseur d’utilisation de la bande passante :</span><span class="sxs-lookup"><span data-stu-id="a719c-236">There are two phases when using Bandwidth Utilization Analyzer:</span></span>

  - <span data-ttu-id="a719c-237">Collecter les journaux, qui sont exécutés à l’aide de WanLinkLogCollector.exe</span><span class="sxs-lookup"><span data-stu-id="a719c-237">Collect logs, which is performed by using WanLinkLogCollector.exe</span></span>

  - <span data-ttu-id="a719c-238">Personnaliser des rapports, qui est effectué à l’aide de BandwidthUtilizationAnalyzer.xlsm</span><span class="sxs-lookup"><span data-stu-id="a719c-238">Customize reports, which is performed by using BandwidthUtilizationAnalyzer.xlsm</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a719c-239">Nous vous recommandons vivement de ne pas lancer manuellement BandwidthUtilizationAnalyzer.xlsm par les utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="a719c-239">We strongly recommend that BandwidthUtilizationAnalyzer.xlsm not be manually launched by end users.</span></span>



</div>

</div>

<div>

## <a name="starting-bandwidth-utilization-analyzer"></a><span data-ttu-id="a719c-240">Démarrage de l’analyseur d’utilisation de la bande passante</span><span class="sxs-lookup"><span data-stu-id="a719c-240">Starting Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="a719c-241">Démarrez WanLinkLogCollector.exe à l’invite de commandes ou à l’aide de l’Explorateur Windows.</span><span class="sxs-lookup"><span data-stu-id="a719c-241">Start WanLinkLogCollector.exe at the command prompt or by using Windows Explorer.</span></span>

<span data-ttu-id="a719c-242">**Utilisation de WanLinkLogCollector.exe**</span><span class="sxs-lookup"><span data-stu-id="a719c-242">**Using WanLinkLogCollector.exe**</span></span>

<span data-ttu-id="a719c-243">Il existe trois étapes à suivre pour utiliser WanLinkLogCollector.exe :</span><span class="sxs-lookup"><span data-stu-id="a719c-243">There are three steps to using WanLinkLogCollector.exe:</span></span>

1.  <span data-ttu-id="a719c-244">**Journalisation de la chronologie**     Fournir la chronologie pour laquelle le rapport doit être généré</span><span class="sxs-lookup"><span data-stu-id="a719c-244">**Log the timeline**   Provide the timeline that the report needs to be generated for</span></span>

2.  <span data-ttu-id="a719c-245">**Spécifier les répertoires**     de fichiers Fournir des informations sur l’emplacement des fichiers</span><span class="sxs-lookup"><span data-stu-id="a719c-245">**Specify the file directories**   Provide file location information</span></span>

3.  <span data-ttu-id="a719c-246">**Collecter les journaux et lancer la visionneuse**    de rapports Exécuter la commande pour générer le rapport</span><span class="sxs-lookup"><span data-stu-id="a719c-246">**Collect the logs and launch the report viewer**  Execute the command to generate the report</span></span>

<div>

## <a name="step-1---log-the-timeline"></a><span data-ttu-id="a719c-247">Étape 1 : journalisation de la chronologie</span><span class="sxs-lookup"><span data-stu-id="a719c-247">Step 1 - Log the timeline</span></span>

<span data-ttu-id="a719c-248">La journalisation de la chronologie permet à l’utilisateur de l’outil de spécifier les éléments suivants, comme illustré dans la figure ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="a719c-248">Logging the timeline allows the tool user to specify the following as shown in the figure below.</span></span>

1.  <span data-ttu-id="a719c-249">**Date de début** Il s’agit de la date de début de la chronologie pour laquelle le rapport doit être généré ; par exemple, le 1er août 2010.</span><span class="sxs-lookup"><span data-stu-id="a719c-249">**Start date** This is the start date of the timeline that the report is to be generated for; for example, August 1, 2010.</span></span>

2.  <span data-ttu-id="a719c-250">**Date de fin** Il s’agit de la date de fin de la chronologie pour laquelle le rapport doit être généré ; par exemple, le 30 septembre 2010.</span><span class="sxs-lookup"><span data-stu-id="a719c-250">**End date** This is the end date of the timeline that the report is to be generated for; for example, September 30, 2010.</span></span>
    
    <span data-ttu-id="a719c-251">![Dates de début et de fin dans l’utilisation de la bande passante](images/JJ945604.2c597cfc-3372-4d41-816b-26202f607ad8(OCS.15).jpg "Dates de début et de fin dans l’utilisation de la bande passante")</span><span class="sxs-lookup"><span data-stu-id="a719c-251">![Start and End dates in the Bandwidth Utilization A](images/JJ945604.2c597cfc-3372-4d41-816b-26202f607ad8(OCS.15).jpg "Start and End dates in the Bandwidth Utilization A")</span></span>  

</div>

<div>

## <a name="step-2---specify-the-file-directories"></a><span data-ttu-id="a719c-252">Étape 2 : spécification des répertoires de fichiers</span><span class="sxs-lookup"><span data-stu-id="a719c-252">Step 2 - Specify the file directories</span></span>

<span data-ttu-id="a719c-253">Les répertoires de fichiers suivants peuvent être spécifiés par l’utilisateur comme indiqué.</span><span class="sxs-lookup"><span data-stu-id="a719c-253">The following file directories can be specified by the user as shown.</span></span>

  - <span data-ttu-id="a719c-254">**Emplacement des fichiers journaux du serveur** Emplacement du dossier dans lequel sont stockés les journaux du serveur de stratégie de bande passante.</span><span class="sxs-lookup"><span data-stu-id="a719c-254">**Server log files location** The folder location where Bandwidth policy server logs are stored.</span></span> <span data-ttu-id="a719c-255">Il s’agit généralement de \<fileserver\> \\ \<choice of FE\> \\ AppServerFiles \\ PDP.</span><span class="sxs-lookup"><span data-stu-id="a719c-255">This is typically in \<fileserver\>\\\<choice of FE\>\\AppServerFiles\\PDP.</span></span>

  - <span data-ttu-id="a719c-256">**Emplacement de stockage des fichiers temporaires** Emplacement du fichier temporaire dans lequel les fichiers intermédiaires sont stockés pendant la génération du rapport.</span><span class="sxs-lookup"><span data-stu-id="a719c-256">**Temporary file storage location** The temporary file location where intermediate files are stored while the report is being generated.</span></span>

<span data-ttu-id="a719c-257">![Répertoires de fichiers dans l’utilisation de la bande passante anal](images/JJ945604.d66daeac-1669-45e3-932d-3f6782840c2a(OCS.15).jpg "Répertoires de fichiers dans l’utilisation de la bande passante anal")</span><span class="sxs-lookup"><span data-stu-id="a719c-257">![File directories in the Bandwidth Utilization Anal](images/JJ945604.d66daeac-1669-45e3-932d-3f6782840c2a(OCS.15).jpg "File directories in the Bandwidth Utilization Anal")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a719c-258">Assurez-vous qu’un accès suffisant aux journaux du serveur et au dossier de magasin de fichiers temporaire est fourni à l’utilisateur de l’outil.</span><span class="sxs-lookup"><span data-stu-id="a719c-258">Ensure that sufficient file access to the server logs and the temporary file store folder is provided to the tool user.</span></span>



</div>

</div>

<div>

## <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a><span data-ttu-id="a719c-259">Étape 3 : collecte des journaux et démarrage de la visionneuse de rapports</span><span class="sxs-lookup"><span data-stu-id="a719c-259">Step 3 - Collect the logs and start the report viewer</span></span>

<span data-ttu-id="a719c-260">Pour collecter les journaux et démarrer la visionneuse de rapports, cliquez sur **exécuter** comme indiqué ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="a719c-260">To collect the logs and start the report viewer, click **Execute** as shown below.</span></span> <span data-ttu-id="a719c-261">Cette étape collecte les données requises.</span><span class="sxs-lookup"><span data-stu-id="a719c-261">This step collects the required data.</span></span>

<span data-ttu-id="a719c-262">![Collecte de données dans l’utilisation de la bande passante](images/JJ945604.0019cb2c-7c01-4dc9-ac90-ac47c47d1bfd(OCS.15).jpg "Collecte de données dans l’utilisation de la bande passante")</span><span class="sxs-lookup"><span data-stu-id="a719c-262">![Collecting data in the Bandwidth Utilization Analy](images/JJ945604.0019cb2c-7c01-4dc9-ac90-ac47c47d1bfd(OCS.15).jpg "Collecting data in the Bandwidth Utilization Analy")</span></span>

<span data-ttu-id="a719c-263">Une fois la validation d’entrée réussie, le message ci-dessous s’affiche.</span><span class="sxs-lookup"><span data-stu-id="a719c-263">When the input validation is successful, the message shown below is displayed.</span></span>

<span data-ttu-id="a719c-264">![Enregistre la notification collectée dans la bande passante utili](images/JJ945604.eda91da8-3285-4eab-8ccb-c6d89c8cc221(OCS.15).jpg "Enregistre la notification collectée dans la bande passante utili")</span><span class="sxs-lookup"><span data-stu-id="a719c-264">![Logs collected notification in the Bandwidth Utili](images/JJ945604.eda91da8-3285-4eab-8ccb-c6d89c8cc221(OCS.15).jpg "Logs collected notification in the Bandwidth Utili")</span></span>

<span data-ttu-id="a719c-265">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a719c-265">Click **OK**.</span></span> <span data-ttu-id="a719c-266">BandwidthUtilizationAnalyzer.xlsm est démarré automatiquement.</span><span class="sxs-lookup"><span data-stu-id="a719c-266">BandwidthUtilizationAnalyzer.xlsm is automatically started.</span></span> <span data-ttu-id="a719c-267">Suivez les instructions indiquées dans la boîte de message.</span><span class="sxs-lookup"><span data-stu-id="a719c-267">Follow the instructions in the message box.</span></span> <span data-ttu-id="a719c-268">Pour plus d’informations, reportez-vous à la rubrique **utilisation de BandwidthUtilizationAnalyzer.xlsm** dans la section suivante.</span><span class="sxs-lookup"><span data-stu-id="a719c-268">For details, see **Using BandwidthUtilizationAnalyzer.xlsm** in the next section.</span></span>

</div>

<div>


<span data-ttu-id="a719c-269">**Utilisation de BandwidthUtilizationAnalyzer.xlsm**</span><span class="sxs-lookup"><span data-stu-id="a719c-269">**Using BandwidthUtilizationAnalyzer.xlsm**</span></span>

1.  <span data-ttu-id="a719c-270">Lorsque BandwidthUtilizationAnalyzer.xlsm est démarré automatiquement, cliquez sur **Actualiser** comme indiqué ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="a719c-270">When BandwidthUtilizationAnalyzer.xlsm is automatically started, click **Refresh** as shown below.</span></span>
    
    <span data-ttu-id="a719c-271">![BandwidthUtilizationAnalyzer.xlsm](images/JJ945604.c4e675b9-1671-400e-a712-6db82d731b39(OCS.15).jpg "BandwidthUtilizationAnalyzer.xlsm")</span><span class="sxs-lookup"><span data-stu-id="a719c-271">![BandwidthUtilizationAnalyzer.xlsm](images/JJ945604.c4e675b9-1671-400e-a712-6db82d731b39(OCS.15).jpg "BandwidthUtilizationAnalyzer.xlsm")</span></span>

2.  <span data-ttu-id="a719c-272">Lors de l’ouverture d’un dossier de fichiers, sélectionnez consolidated.csv à partir de l’emplacement spécifié dans la zone de message, comme indiqué ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="a719c-272">When a file folder is opened, select consolidated.csv from the location that is specified in the message box as shown below.</span></span> <span data-ttu-id="a719c-273">Il indique également l’emplacement sous la forme **C : \\ temp**.</span><span class="sxs-lookup"><span data-stu-id="a719c-273">It also shows the location as **C:\\Temp**.</span></span>
    
    <span data-ttu-id="a719c-274">![Ouverture d’un dossier dans BandwidthUtilizationAnalyzer.](images/JJ945604.601cc572-cee9-45fb-9ed1-c4b96a2fa21e(OCS.15).jpg "Ouverture d’un dossier dans BandwidthUtilizationAnalyzer.")</span><span class="sxs-lookup"><span data-stu-id="a719c-274">![Opening a folder in BandwidthUtilizationAnalyzer.](images/JJ945604.601cc572-cee9-45fb-9ed1-c4b96a2fa21e(OCS.15).jpg "Opening a folder in BandwidthUtilizationAnalyzer.")</span></span>

3.  <span data-ttu-id="a719c-275">Cliquez sur **Importer**.</span><span class="sxs-lookup"><span data-stu-id="a719c-275">Click **Import**.</span></span>

4.  <span data-ttu-id="a719c-276">Le tracé graphique est généré automatiquement.</span><span class="sxs-lookup"><span data-stu-id="a719c-276">The graphical plot is automatically generated.</span></span> <span data-ttu-id="a719c-277">Elle est disponible lorsque le pointeur de travail en arrière-plan disparaît.</span><span class="sxs-lookup"><span data-stu-id="a719c-277">It is available when the working-in-the-background pointer disappears.</span></span>
    
    <span data-ttu-id="a719c-278">![Application de filtres en mode état.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Application de filtres en mode état.")</span><span class="sxs-lookup"><span data-stu-id="a719c-278">![Applying filters in Report View.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Applying filters in Report View.")</span></span>

</div>

<div>

## <a name="applying-filters-to-the-report-view"></a><span data-ttu-id="a719c-279">Application de filtres à l’affichage de rapport</span><span class="sxs-lookup"><span data-stu-id="a719c-279">Applying Filters to the Report View</span></span>

<span data-ttu-id="a719c-280">Les filtres qui peuvent être appliqués à l’affichage de rapport comme indiqué ci-dessous sont décrits comme suit :</span><span class="sxs-lookup"><span data-stu-id="a719c-280">The filters that can be applied to the report view as shown below are described as follows:</span></span>

<span data-ttu-id="a719c-281">![Application de filtres en mode état.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Application de filtres en mode état.")</span><span class="sxs-lookup"><span data-stu-id="a719c-281">![Applying filters in Report View.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Applying filters in Report View.")</span></span>

1.  <span data-ttu-id="a719c-282">**Name (nom** ) Filtrer par liaisons WAN (le filtre se trouve sur le côté droit du graphique). Le préfixe indique les types de liens suivants : consultez la zone vertical (bleu) :</span><span class="sxs-lookup"><span data-stu-id="a719c-282">**Name** Filter by WAN links (the filter is on the right side of the graph).The prefix denotes the following link types; see the vertical (blue) box:</span></span>
    
      - <span data-ttu-id="a719c-283">**Site S** Liaison WAN entre un site réseau et une région réseau</span><span class="sxs-lookup"><span data-stu-id="a719c-283">**S Site** The WAN link from a network site to a network region</span></span>
    
      - <span data-ttu-id="a719c-284">**Est inter-site** La liaison de réseau étendu entre deux sites réseau</span><span class="sxs-lookup"><span data-stu-id="a719c-284">**IS Inter-Site** The WAN link between two network sites</span></span>
    
      - <span data-ttu-id="a719c-285">**R inter-région** La liaison de réseau étendu entre deux régions réseau</span><span class="sxs-lookup"><span data-stu-id="a719c-285">**R Inter-Region** The WAN link between two network region</span></span>

2.  <span data-ttu-id="a719c-286">**Limite dépassée** Filtrer par des liaisons de réseau étendu dont l’utilisation de la bande passante est supérieure à la capacité de bande passante</span><span class="sxs-lookup"><span data-stu-id="a719c-286">**Exceeded limit** Filter by WAN links whose bandwidth utilization is more than the bandwidth capacity</span></span>

3.  <span data-ttu-id="a719c-287">**Niveaux critiques** Filtrer par des liaisons de réseau étendu dont l’utilisation de la bande passante atteint 90% ou plus de la capacité de bande passante</span><span class="sxs-lookup"><span data-stu-id="a719c-287">**Critical levels** Filter by WAN links whose bandwidth utilization has reached 90% or more than the bandwidth capacity</span></span>

4.  <span data-ttu-id="a719c-288">**Sous-utilisés** Filtrer par des liaisons de réseau étendu dont l’utilisation de la bande passante est inférieure à 25% de la capacité de bande passante</span><span class="sxs-lookup"><span data-stu-id="a719c-288">**Under-utilized** Filter by WAN links whose bandwidth utilization has been less than 25% of the bandwidth capacity</span></span>

5.  <span data-ttu-id="a719c-289">**Type de liaison** Filtrez les types de liaisons de réseau étendu suivants :</span><span class="sxs-lookup"><span data-stu-id="a719c-289">**Link type** Filter by the following WAN links types:</span></span>
    
      - <span data-ttu-id="a719c-290">Type de **site réseau**</span><span class="sxs-lookup"><span data-stu-id="a719c-290">**Network site** type</span></span>
    
      - <span data-ttu-id="a719c-291">Type **inter-sites**</span><span class="sxs-lookup"><span data-stu-id="a719c-291">**Inter-site** type</span></span>
    
      - <span data-ttu-id="a719c-292">Type **de lien entre les régions**</span><span class="sxs-lookup"><span data-stu-id="a719c-292">**Inter-Region link** type</span></span>

6.  <span data-ttu-id="a719c-293">**Région** Filtrer par région réseau</span><span class="sxs-lookup"><span data-stu-id="a719c-293">**Region** Filter by network region</span></span>

<span data-ttu-id="a719c-294">Les figures suivantes présentent les filtres décrits précédemment.</span><span class="sxs-lookup"><span data-stu-id="a719c-294">The following figures show the previously described filters.</span></span>

<span data-ttu-id="a719c-295">Filtrez par **nom**.</span><span class="sxs-lookup"><span data-stu-id="a719c-295">Filter by **Name**.</span></span> <span data-ttu-id="a719c-296">Sélectionnez la liste des liens à afficher dans le graphique.</span><span class="sxs-lookup"><span data-stu-id="a719c-296">Select the list of links that need to be displayed in the graph.</span></span>

<span data-ttu-id="a719c-297">![Filtrage par nom dans BandwidthUtilizationAnalyzer.](images/JJ945604.002b7c8e-f0da-48ce-9e1a-5c34d2cab063(OCS.15).jpg "Filtrage par nom dans BandwidthUtilizationAnalyzer.")</span><span class="sxs-lookup"><span data-stu-id="a719c-297">![Filtering by Name in BandwidthUtilizationAnalyzer.](images/JJ945604.002b7c8e-f0da-48ce-9e1a-5c34d2cab063(OCS.15).jpg "Filtering by Name in BandwidthUtilizationAnalyzer.")</span></span>

<span data-ttu-id="a719c-298">Filtre par **limite dépassée**.</span><span class="sxs-lookup"><span data-stu-id="a719c-298">Filter by **Exceeded limit**.</span></span> <span data-ttu-id="a719c-299">Sélectionnez **true** pour appliquer le filtre.</span><span class="sxs-lookup"><span data-stu-id="a719c-299">Select **True** to enforce the filter.</span></span>

<span data-ttu-id="a719c-300">![Filtrage par limite dépassée.](images/JJ945604.5946c95e-76ce-46ca-8f3e-a79be1e5c527(OCS.15).jpg "Filtrage par limite dépassée.")</span><span class="sxs-lookup"><span data-stu-id="a719c-300">![Filtering by Exceeded Limit.](images/JJ945604.5946c95e-76ce-46ca-8f3e-a79be1e5c527(OCS.15).jpg "Filtering by Exceeded Limit.")</span></span>

<span data-ttu-id="a719c-301">Filtrer par **niveaux critiques**.</span><span class="sxs-lookup"><span data-stu-id="a719c-301">Filter by **Critical levels**.</span></span> <span data-ttu-id="a719c-302">Sélectionnez **true** pour appliquer le filtre.</span><span class="sxs-lookup"><span data-stu-id="a719c-302">Select **True** to enforce the filter.</span></span>

<span data-ttu-id="a719c-303">![Filtrage par niveaux critiques.](images/JJ945604.60771a52-d8ba-4cb9-a02d-d6c888cb5505(OCS.15).jpg "Filtrage par niveaux critiques.")</span><span class="sxs-lookup"><span data-stu-id="a719c-303">![Filtering by Critical Levels.](images/JJ945604.60771a52-d8ba-4cb9-a02d-d6c888cb5505(OCS.15).jpg "Filtering by Critical Levels.")</span></span>

<span data-ttu-id="a719c-304">Filtrer par **sous-utilisé**.</span><span class="sxs-lookup"><span data-stu-id="a719c-304">Filter by **Under utilized**.</span></span> <span data-ttu-id="a719c-305">Sélectionnez **true** pour appliquer le filtre.</span><span class="sxs-lookup"><span data-stu-id="a719c-305">Select **True** to enforce the filter.</span></span>

<span data-ttu-id="a719c-306">![Filtrage par sous-utilisé.](images/JJ945604.95a2bf01-5aba-4927-af47-1ad3c459d791(OCS.15).jpg "Filtrage par sous-utilisé.")</span><span class="sxs-lookup"><span data-stu-id="a719c-306">![Filtering by Under Utilized.](images/JJ945604.95a2bf01-5aba-4927-af47-1ad3c459d791(OCS.15).jpg "Filtering by Under Utilized.")</span></span>

<span data-ttu-id="a719c-307">Filtre par **type de lien**.</span><span class="sxs-lookup"><span data-stu-id="a719c-307">Filter by **Link Type**.</span></span> <span data-ttu-id="a719c-308">Sélectionnez le ou les types à afficher.</span><span class="sxs-lookup"><span data-stu-id="a719c-308">Select the type or types that need to be displayed.</span></span>

<span data-ttu-id="a719c-309">![Filtrage par type de lien.](images/JJ945604.08757949-06bd-4cf3-809f-d81fd23a6639(OCS.15).jpg "Filtrage par type de lien.")</span><span class="sxs-lookup"><span data-stu-id="a719c-309">![Filtering by Link Type.](images/JJ945604.08757949-06bd-4cf3-809f-d81fd23a6639(OCS.15).jpg "Filtering by Link Type.")</span></span>

<span data-ttu-id="a719c-310">Filtrez par **région**.</span><span class="sxs-lookup"><span data-stu-id="a719c-310">Filter by **Region**.</span></span> <span data-ttu-id="a719c-311">Sélectionnez la liste des régions dont les liens doivent être affichés.</span><span class="sxs-lookup"><span data-stu-id="a719c-311">Select a list of regions whose links need to be displayed.</span></span>

<span data-ttu-id="a719c-312">![Filtrage par région.](images/JJ945604.5de4cec4-6c09-48bb-98c7-b56f7bdb3d5a(OCS.15).jpg "Filtrage par région.")</span><span class="sxs-lookup"><span data-stu-id="a719c-312">![Filtering by Region.](images/JJ945604.5de4cec4-6c09-48bb-98c7-b56f7bdb3d5a(OCS.15).jpg "Filtering by Region.")</span></span>

</div>

</div>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="a719c-313">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="a719c-313">Requirements</span></span>

  - <span data-ttu-id="a719c-314">.NET Framework 3,5</span><span class="sxs-lookup"><span data-stu-id="a719c-314">The .NET Framework 3.5</span></span>

  - <span data-ttu-id="a719c-315">Microsoft Excel 2010 ou Excel 2007</span><span class="sxs-lookup"><span data-stu-id="a719c-315">Microsoft Excel 2010 or Excel 2007</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="a719c-316">Résumé</span><span class="sxs-lookup"><span data-stu-id="a719c-316">Summary</span></span>

<span data-ttu-id="a719c-317">L’analyseur d’utilisation de la bande passante permet de tracer l’utilisation de la bande passante audio pour le trafic UC sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="a719c-317">Bandwidth Utilization Analyzer is used to plot the audio bandwidth utilization for UC traffic across the network.</span></span> <span data-ttu-id="a719c-318">Cet outil peut également être utilisé pour signaler l’utilisation de la bande passante vidéo sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="a719c-318">This tool can be used to report the utilization of video bandwidth on the network as well.</span></span>

</div>

</div>

<div>

## <a name="call-parkometer"></a><span data-ttu-id="a719c-319">Appeler Parkometer</span><span class="sxs-lookup"><span data-stu-id="a719c-319">Call Parkometer</span></span>

<span data-ttu-id="a719c-320">Call Parkometer est une application en ligne de commande qui fournit un accès facile à la base de données des orbites de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="a719c-320">Call Parkometer is a command-line application that provides easy access to the Call Park orbit database.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="a719c-321">Description</span><span class="sxs-lookup"><span data-stu-id="a719c-321">Description</span></span>

<span data-ttu-id="a719c-322">Call Parkometer est un outil permettant de suivre les appels actuellement parqués.</span><span class="sxs-lookup"><span data-stu-id="a719c-322">Call Parkometer is a tool to track currently parked calls.</span></span> <span data-ttu-id="a719c-323">Il collecte également des statistiques sur les orbites et l’utilisation du serveur de parcage d’appel (CPS).</span><span class="sxs-lookup"><span data-stu-id="a719c-323">It also collects statistics about orbits and Call Park Server (CPS) usage.</span></span> <span data-ttu-id="a719c-324">Cet outil de ligne de commande fournit à la fois un accès en lecture et en écriture à la base de données SQL Server d’orbites CPS à partir d’un ordinateur local ou connecté à distance.</span><span class="sxs-lookup"><span data-stu-id="a719c-324">This command-line tool provides both read and write-access to the CPS orbit SQL Server database from a local or remotely connected computer.</span></span>

<span data-ttu-id="a719c-325">Toutes les options s’excluent mutuellement.</span><span class="sxs-lookup"><span data-stu-id="a719c-325">All options are mutually exclusive.</span></span> <span data-ttu-id="a719c-326">La syntaxe de la ligne de commande est la suivante :</span><span class="sxs-lookup"><span data-stu-id="a719c-326">Command-line syntax is as follows:</span></span>

  - <span data-ttu-id="a719c-327">paramètre **– o** : répertorie toutes les plages d’orbites configurées pour ce pool.</span><span class="sxs-lookup"><span data-stu-id="a719c-327">**–o** parameter—lists all orbit ranges configured for this pool.</span></span>

  - <span data-ttu-id="a719c-328">paramètre **– n** : répertorie toutes les orbites actuellement utilisées dans ce pool.</span><span class="sxs-lookup"><span data-stu-id="a719c-328">**–n** parameter—lists all currently used orbits in this pool.</span></span> <span data-ttu-id="a719c-329">Les informations affichées sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="a719c-329">The information displayed is as follows:</span></span>
    
      - <span data-ttu-id="a719c-330">URI (Uniform Resource Identifier) SIP du parqué et parqueur.</span><span class="sxs-lookup"><span data-stu-id="a719c-330">SIP Uniform Resource Identifier (URI) of the parkee and parker.</span></span>
    
      - <span data-ttu-id="a719c-331">Nom d’hôte du CPS dans lequel l’appel est parqué.</span><span class="sxs-lookup"><span data-stu-id="a719c-331">Host name of the CPS where the call is parked.</span></span>
    
      - <span data-ttu-id="a719c-332">Horodatage du moment où l’appel a été parqué.</span><span class="sxs-lookup"><span data-stu-id="a719c-332">Time stamp of when the call was parked.</span></span>

  - <span data-ttu-id="a719c-333">**– paramètre f** — indique le nombre d’orbites libres actuellement dans le pool.</span><span class="sxs-lookup"><span data-stu-id="a719c-333">**–f** parameter—lists the number of currently free orbits in the pool.</span></span>

  - <span data-ttu-id="a719c-334">\*\*– r \<n\> \*\* paramètre : répertorie les \<n\> derniers appels parqués.</span><span class="sxs-lookup"><span data-stu-id="a719c-334">**–r \<n\>** parameter—lists the \<n\> last parked calls.</span></span> <span data-ttu-id="a719c-335">Les informations affichées sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="a719c-335">The information displayed is as follows:</span></span>
    
      - <span data-ttu-id="a719c-336">URI SIP du parcage.</span><span class="sxs-lookup"><span data-stu-id="a719c-336">Parkee SIP URI.</span></span>
    
      - <span data-ttu-id="a719c-337">URI SIP parqueur.</span><span class="sxs-lookup"><span data-stu-id="a719c-337">Parker SIP URI.</span></span>
    
      - <span data-ttu-id="a719c-338">Nom d’hôte du CPS sur lequel l’appel a été parqué.</span><span class="sxs-lookup"><span data-stu-id="a719c-338">Host name of the CPS where the call was parked.</span></span>
    
      - <span data-ttu-id="a719c-339">Horodatage de l’extraction ou de la suppression de l’appel.</span><span class="sxs-lookup"><span data-stu-id="a719c-339">Time stamp of when the call was retrieved or dropped.</span></span>

  - <span data-ttu-id="a719c-340">\*\*-t \<n\> \*\* paramètre-tests de réservation d’une orbite dans la base de données pour afficher le caractère aléatoire des numéros d’orbite attribués.</span><span class="sxs-lookup"><span data-stu-id="a719c-340">**-t\<n\>** parameter - tests reserving an orbit in the database to show the randomness of the assigned orbit numbers.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="a719c-341">Output</span><span class="sxs-lookup"><span data-stu-id="a719c-341">Output</span></span>

<span data-ttu-id="a719c-342">En fonction des paramètres d’entrée spécifiés à l’invite de commandes, appelez Parkometer affiche la sortie suivante :</span><span class="sxs-lookup"><span data-stu-id="a719c-342">Depending on the input parameters that are specified at a command prompt, Call Parkometer displays the following output:</span></span>

  - <span data-ttu-id="a719c-343">Toutes les plages d’orbites configurées pour ce pool</span><span class="sxs-lookup"><span data-stu-id="a719c-343">All orbit ranges that are configured for this pool</span></span>

  - <span data-ttu-id="a719c-344">Appels actuellement parqués</span><span class="sxs-lookup"><span data-stu-id="a719c-344">Currently parked calls</span></span>

  - <span data-ttu-id="a719c-345">Nombre d’orbites libres (disponibles)</span><span class="sxs-lookup"><span data-stu-id="a719c-345">Number of free (available) orbits</span></span>

  - <span data-ttu-id="a719c-346">Appels parqués récemment</span><span class="sxs-lookup"><span data-stu-id="a719c-346">Recently parked calls</span></span>

  - <span data-ttu-id="a719c-347">Orbites réservées pour le test des valeurs d’orbite uniforme et aléatoire</span><span class="sxs-lookup"><span data-stu-id="a719c-347">Reserved orbits for testing uniform and random orbit values</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="a719c-348">Objectif</span><span class="sxs-lookup"><span data-stu-id="a719c-348">Purpose</span></span>

<span data-ttu-id="a719c-349">L’objectif de l’outil CPS est de fournir un accès à la base de données CPS à partir de la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="a719c-349">The purpose of the CPS tool is to provide command-line access to the CPS database.</span></span> <span data-ttu-id="a719c-350">L’administrateur peut consulter l’utilisation de CPS et déterminer le nombre d’orbites affectées à un pool.</span><span class="sxs-lookup"><span data-stu-id="a719c-350">The administrator can view the CPS usage and determine the number of orbits assigned to a pool.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="a719c-351">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="a719c-351">Requirements</span></span>

<span data-ttu-id="a719c-352">Il n’y a aucune condition requise si cet outil est exécuté sur le même ordinateur que celui qui exécute CPS.</span><span class="sxs-lookup"><span data-stu-id="a719c-352">There are no requirements if this tool is run on the same computer that is running CPS.</span></span> <span data-ttu-id="a719c-353">Si cet outil est exécuté sur un ordinateur distant, la base de données SQL Server utilisée par Lync Server 2013 doit être configurée pour autoriser l’accès à distance.</span><span class="sxs-lookup"><span data-stu-id="a719c-353">If this tool is run on a remote computer, the SQL Server database used by Lync Server 2013 must be configured to allow remote access.</span></span> <span data-ttu-id="a719c-354">Call Parkometer doit être configuré avec une chaîne de connexion de base de données SQL Server pour se connecter au serveur SQL Server du pool.</span><span class="sxs-lookup"><span data-stu-id="a719c-354">Call Parkometer must be configured with a SQL Server database connection string to connect to the pool’s SQL Server.</span></span> <span data-ttu-id="a719c-355">Cette chaîne de connexion de base de données SQL Server est définie dans le fichier de configuration, **parkometer.exe.config**. Il doit être placé dans le répertoire où se trouve parkometer.exe.</span><span class="sxs-lookup"><span data-stu-id="a719c-355">This SQL Server database connection string is defined in the configuration file, **parkometer.exe.config**. It must be placed in the same directory where parkometer.exe is located.</span></span> <span data-ttu-id="a719c-356">Le fichier XML suivant est un exemple de parkometer.exe.config. Les paramètres qui doivent être configurés sont le nom d’utilisateur (par exemple, \\ administrateur mondomaine), le mot de passe (par exemple, monmotdepasse) et le nom d’hôte (par exemple, monserveur).</span><span class="sxs-lookup"><span data-stu-id="a719c-356">The following XML file is an example of a parkometer.exe.config. The parameters that must be configured are user name (for example, mydomain\\Administrator), password (for example, mypassword), and host name (for example, myserver).</span></span>

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

</div>

<div>

## <a name="examples"></a><span data-ttu-id="a719c-357">Exemples</span><span class="sxs-lookup"><span data-stu-id="a719c-357">Examples</span></span>

<span data-ttu-id="a719c-358">Plages d’orbites déployées : le paramètre – o répertorie toutes les plages d’orbites configurées pour ce pool, comme indiqué</span><span class="sxs-lookup"><span data-stu-id="a719c-358">Deployed orbit ranges: the –o parameter lists all orbit ranges that are configured for this pool as shown</span></span>

<span data-ttu-id="a719c-359">![Plages d’orbites dans l’appel Parkometer.](images/JJ945604.9ede64cb-29d9-4782-a34b-b76c42fbdcad(OCS.15).jpg "Plages d’orbites dans l’appel Parkometer.")</span><span class="sxs-lookup"><span data-stu-id="a719c-359">![Orbit ranges in Call Parkometer.](images/JJ945604.9ede64cb-29d9-4782-a34b-b76c42fbdcad(OCS.15).jpg "Orbit ranges in Call Parkometer.")</span></span>

<span data-ttu-id="a719c-360">Appels actuellement parqués : le paramètre – n répertorie toutes les orbites actuellement utilisées sur ce pool, comme illustré ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="a719c-360">Currently parked calls: the –n parameter lists all currently used orbits on this pool as shown</span></span>

<span data-ttu-id="a719c-361">![Appels actuellement parqués dans Call Parkometer.](images/JJ945604.07a7eec4-7999-4c92-93f0-95525b244b4c(OCS.15).jpg "Appels actuellement parqués dans Call Parkometer.")</span><span class="sxs-lookup"><span data-stu-id="a719c-361">![Currently-parked calls in Call Parkometer.](images/JJ945604.07a7eec4-7999-4c92-93f0-95525b244b4c(OCS.15).jpg "Currently-parked calls in Call Parkometer.")</span></span>

<span data-ttu-id="a719c-362">Nombre d’orbites libres : le paramètre – f indique le nombre d’orbites libres actuellement dans le pool, comme indiqué</span><span class="sxs-lookup"><span data-stu-id="a719c-362">Number of free orbits: the –f parameter lists the number of currently free orbits in the pool as shown</span></span>

<span data-ttu-id="a719c-363">![Orbites libres dans l’appel Parkometer.](images/JJ945604.ecc1d621-0ca0-4ecf-a579-08b41c6f08ed(OCS.15).jpg "Orbites libres dans l’appel Parkometer.")</span><span class="sxs-lookup"><span data-stu-id="a719c-363">![Free orbits in Call Parkometer.](images/JJ945604.ecc1d621-0ca0-4ecf-a579-08b41c6f08ed(OCS.15).jpg "Free orbits in Call Parkometer.")</span></span>

<span data-ttu-id="a719c-364">Appels parqués récemment : le paramètre – r \<n\> répertorie les \<n\> derniers appels parqués, comme illustré ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="a719c-364">Recently parked calls: the –r \<n\> parameter lists the \<n\> last parked calls as shown</span></span>

<span data-ttu-id="a719c-365">![Appels parqués récemment dans Call Parkometer.](images/JJ945604.1c5eb27d-faa1-491b-b4aa-b484255c3353(OCS.15).jpg "Appels parqués récemment dans Call Parkometer.")</span><span class="sxs-lookup"><span data-stu-id="a719c-365">![Recently-parked calls in Call Parkometer.](images/JJ945604.1c5eb27d-faa1-491b-b4aa-b484255c3353(OCS.15).jpg "Recently-parked calls in Call Parkometer.")</span></span>

<span data-ttu-id="a719c-366">Réservation d’orbites de test : le paramètre – t \<n\> teste la réservation d’une orbite dans la base de données, comme illustré</span><span class="sxs-lookup"><span data-stu-id="a719c-366">Test orbit reservation: the –t \<n\> parameter tests reserving an orbit in the database as shown</span></span>

<span data-ttu-id="a719c-367">![Testez les réservations d’orbites dans Call Parkometer.](images/JJ945604.84c9b69e-7af0-4224-8711-a43a28f08691(OCS.15).jpg "Testez les réservations d’orbites dans Call Parkometer.")</span><span class="sxs-lookup"><span data-stu-id="a719c-367">![Test orbit reservations in Call Parkometer.](images/JJ945604.84c9b69e-7af0-4224-8711-a43a28f08691(OCS.15).jpg "Test orbit reservations in Call Parkometer.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="a719c-368">Résumé</span><span class="sxs-lookup"><span data-stu-id="a719c-368">Summary</span></span>

<span data-ttu-id="a719c-369">Call Parkometer est un outil de ligne de commande qui fournit des informations détaillées sur le serveur de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="a719c-369">Call Parkometer is a command-line tool that provides detailed information about the Call Park Server.</span></span>

</div>

</div>

<div>

## <a name="cleanupstorageservicedata"></a><span data-ttu-id="a719c-370">CleanupStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="a719c-370">CleanupStorageServiceData</span></span>

<span data-ttu-id="a719c-371">L’outil Kit de ressources de CleanupStorageServiceData permet de supprimer des données orphelines de la base de données utilisée par le service de stockage Lync Server (LYSS).</span><span class="sxs-lookup"><span data-stu-id="a719c-371">The CleanupStorageServiceData resource kit tool allows for deleting of orphaned data from the database used by the Lync Server Storage Service (LYSS).</span></span> <span data-ttu-id="a719c-372">Une des fonctions du service de stockage est de mettre en mémoire tampon les communications entre Lync Server et différents points de terminaison de stockage de données principales, tels que SQL Server et Exchange.</span><span class="sxs-lookup"><span data-stu-id="a719c-372">One function of the storage service is to buffer communication between Lync Server and various back-end data storage endpoints, like SQL Server and Exchange.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="a719c-373">Description</span><span class="sxs-lookup"><span data-stu-id="a719c-373">Description</span></span>

<span data-ttu-id="a719c-374">Pour prendre en charge la haute disponibilité, LYSS accepte et enregistre temporairement des copies des données sur plusieurs serveurs frontaux dans le pool, et supprime ces données une fois qu’il a été remis à son emplacement de stockage à long terme.</span><span class="sxs-lookup"><span data-stu-id="a719c-374">To support high availability, LYSS accepts and saves copies of the data on multiple front end servers in the pool temporarily, and removes that data once it has been delivered to its final long-term storage location.</span></span> <span data-ttu-id="a719c-375">Il existe des situations inhabituelles pouvant se produire pendant une opération normale, lorsqu’un serveur peut se bloquer ou rencontrer un problème de traitement et que certaines données risquent de ne pas être nettoyées correctement.</span><span class="sxs-lookup"><span data-stu-id="a719c-375">There are unusual situations which may occur during otherwise normal operation, when a server might crash or experience a processing issue, and some data might not get cleaned up properly.</span></span> <span data-ttu-id="a719c-376">Ces données sont inoffensives, mais elles consomment des ressources de traitement limitées.</span><span class="sxs-lookup"><span data-stu-id="a719c-376">This data is harmless, but it does consume limited processing resources.</span></span> <span data-ttu-id="a719c-377">Une grande part de la maintenance des données requises normale est automatisée, mais cet outil permet l’identification et la suppression sûres de ces données orphelines lorsque la suppression automatique n’est pas possible.</span><span class="sxs-lookup"><span data-stu-id="a719c-377">Much of the normal required data maintenance is automated, but this tool allows for the safe identification and removal of such orphaned data when automated removal is not possible.</span></span> <span data-ttu-id="a719c-378">L’utilisation de cet outil est indiquée lorsqu’une alerte de System Center Operations Manager (SCOM) de surveillance de l’intégrité est générée, qui demande à l’administrateur de supprimer les données inutiles des bases de données LYSS locales dans le pool.</span><span class="sxs-lookup"><span data-stu-id="a719c-378">Usage of this tool is indicated when a health monitoring System Center Operations Manager (SCOM) alert is raised which asks the administrator to remove the unneeded data from the local LYSS databases in the pool.</span></span> <span data-ttu-id="a719c-379">Il y aura un événement correspondant dans le journal des événements sur le serveur frontal qui a déclenché l’alerte.</span><span class="sxs-lookup"><span data-stu-id="a719c-379">There will be a corresponding event in the event log on the front end which triggered the alert.</span></span> <span data-ttu-id="a719c-380">Les détails de l’événement contiendront des informations sur la quantité de données orphelines contenues sur le serveur frontal et sont déclenchés lorsque ces données dépassent certains seuils préalablement définis.</span><span class="sxs-lookup"><span data-stu-id="a719c-380">The event details will contain information about the amount of orphaned data contained on the front end, and is raised when that data exceeds certain pre-determine thresholds</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="a719c-381">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="a719c-381">Requirements</span></span>

<span data-ttu-id="a719c-382">Installez les outils du kit de ressources Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a719c-382">Install the Lync Server 2013, Resource Kit Tools.</span></span> <span data-ttu-id="a719c-383">L’outil s’exécute sur des ordinateurs liés à un domaine sur lesquels Lync Server et Lync Server 2013 Management Shell sont installés.</span><span class="sxs-lookup"><span data-stu-id="a719c-383">The tool runs on domain-joined machines where Lync Server and Lync Server 2013 Management Shell are installed.</span></span> <span data-ttu-id="a719c-384">L’outil utilise une cmdlet de Management Shell pour identifier tous les serveurs frontaux dans le pool.</span><span class="sxs-lookup"><span data-stu-id="a719c-384">The tool uses a cmdlet from the management shell to identify all Front End servers in the pool.</span></span> <span data-ttu-id="a719c-385">Deuxièmement, l’outil doit être exécuté à partir d’un ordinateur du pool sur lequel la base de données **RtcLocal** est installée.</span><span class="sxs-lookup"><span data-stu-id="a719c-385">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="a719c-386">Cette base de données est utilisée par l’outil CleanupStorageServiceData pour obtenir les détails de connexion nécessaires pour communiquer avec le service de routage Lync Server. Enfin, le compte ou les informations d’identification appelant l’outil doivent disposer d’une autorisation en lecture/écriture sur le partage de fichiers auquel ils souhaitent écrire le journal de sortie. En outre, cet outil dépend du pool en état stable.</span><span class="sxs-lookup"><span data-stu-id="a719c-386">This database is used by the CleanupStorageServiceData tool to get the connection details needed to communicate with the Lync Server Routing Service.Finally, the account or credential invoking the tool must have read/write permission to the file share to which they want to write the output log.Also, this tool depends on the pool being in a stable state.</span></span> <span data-ttu-id="a719c-387">En essence, cela signifie que chaque serveur frontal doit être opérationnel et que l’instance SQL Server LYNCLOCAL et la base de données LYSS doivent pouvoir être connectées, et chaque groupe de routage doit disposer d’un ensemble complet de 1 serveur frontal principal et de deux serveurs frontaux secondaires.</span><span class="sxs-lookup"><span data-stu-id="a719c-387">In essence this means that every Front End server is expected to be up and running, the SQL Server LYNCLOCAL instance and LYSS database must be able to be connected to, and each routing group must have a complete set of 1 primary Front End servers and 2 secondary Front End servers.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="a719c-388">Exemples</span><span class="sxs-lookup"><span data-stu-id="a719c-388">Examples</span></span>

<span data-ttu-id="a719c-389">C : \\ Program Files \\ Microsoft Lync Server 2013 \\ reskit \\ StorageService \> ImportStorageServiceData.exe</span><span class="sxs-lookup"><span data-stu-id="a719c-389">C:\\Program Files\\Microsoft Lync Server 2013\\ResKit\\StorageService\> ImportStorageServiceData.exe</span></span>

    Description:
    This tool will remove orphaned data from the Storage Service database
    for a pool. You are required to run this tool on a machine inside the
    pool which has the Lync Server Management Shell installed and has RtcLocal database installed.
    Usage: Default behavior is to clean up orphaned data from the all the 
           Storage Service databases in the current pool.
    Additional Options:
    -Verbose    : Turn verbose output on.
    -LogPath    : The UNC path to which to write the log.
    ------------------------------------------------------------------------------
    Please wait while we initialize...
    Found 4 front end servers
    Replica Instances for LYSS Service
    Address: server2.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server1.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server3.vdomain.com - Primaries: 7 Secondaries: 14
    Primary Total Count = 28, Secondary Total Count = 56
    Finding and removing orphaned data for 28 routing groups
    Removing 1 stale groups from FE server.vdomain.com
    No stale routing groups detected on FE server2.vdomain.com
    No stale routing groups detected on FE server1.vdomain.com
    No stale routing groups detected on FE server3.vdomain.com
    Searching for stale queue items
    Removed 20 stale queue items for routing group 17D5435AE40259F7BBDF1866776386E4
    No stale queue items found for routing group 1975349662315F90B119DACB4F2AE3AD
    No stale queue items found for routing group 1A23E3D58BDB5A458A0B73F34AB7ACBE
    No stale queue items found for routing group 1AC91E3A1029535A80123121989CEADC
    No stale queue items found for routing group 3313935458E35B9B9759E08A15D251E6
    No stale queue items found for routing group 39BB0035B06B5427873FC6099720462A
    No stale queue items found for routing group 40721948E7B55CE893A53E911F76D185
    No stale queue items found for routing group 4501E04EAE4856059346949FF817C220
    No stale queue items found for routing group 4D833C98801F546F8E45E417EE028E2E
    No stale queue items found for routing group 5AD77443AD955A22A876749BE66D5317
    No stale queue items found for routing group 69844A271E6C5633A1F2B46A42287DD6
    No stale queue items found for routing group 69DA3BE407A95C7284EB4B1337718C93
    No stale queue items found for routing group 8437358AB34A5CC8967D5EF39494AB8D
    No stale queue items found for routing group 8ED455B1789655359816E1C5BF4C430F
    No stale queue items found for routing group 904F6C9B8AC951AE8B3C86684D3832E4
    No stale queue items found for routing group 90AAB3AE9A1950E0ADE7809A27021D63
    No stale queue items found for routing group 944F5724C65C5F93900DC1C8C898B102
    No stale queue items found for routing group 9E8A2630250C51769E39F63F0FB552BA
    No stale queue items found for routing group A11E27AE439A582288D4657EDA86B565
    No stale queue items found for routing group A9B10C76E764556FAEA3E47301EDF518
    No stale queue items found for routing group AEA2699E74ED59848ACEA7896699430D
    No stale queue items found for routing group B269961603E75065AFDA4F4F006DA5E4
    No stale queue items found for routing group BB873D9A3DA959DAB2FD743E5AA619F7
    No stale queue items found for routing group BCC6A48FBA2454B79B9EDB276657A404
    No stale queue items found for routing group C8EF4805722B5F6C876EBC0440B420FD
    No stale queue items found for routing group CA38EBDAC4845489ACE208C2240E4056
    No stale queue items found for routing group F5921887DB025C5F908CE42DB7F1AEE8
    No stale queue items found for routing group F9E606A825395422B3BF7A01ECBB7B1F
    Writing log: M:\Dev\Server\ResKit\StorageService\CleanupStorageServiceData.Log_20121009_151040
    Tool has finished execution.  Errors encountered: 0
    C:\Program Files\Microsoft Lync Server 2013\ResKit\StorageService>

</div>

</div>

<div>

## <a name="dbanalyze"></a><span data-ttu-id="a719c-390">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="a719c-390">DBAnalyze</span></span>

<div>

## <a name="description"></a><span data-ttu-id="a719c-391">Description</span><span class="sxs-lookup"><span data-stu-id="a719c-391">Description</span></span>

<span data-ttu-id="a719c-392">DBAnalyze est un outil de ligne de commande qui aide les administrateurs à rassembler des rapports d’analyse sur les bases de données Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a719c-392">DBAnalyze is a command-line tool that helps administrators to gather analysis reports about the Lync Server 2013 databases.</span></span> <span data-ttu-id="a719c-393">DBAnalyze présente les modes suivants : diagnostic, données utilisateur, Conférence, MCU et fragmentation de disque :</span><span class="sxs-lookup"><span data-stu-id="a719c-393">DBAnalyze has the following modes: diagnostic, user data, conference, MCUs, and disk fragmentation:</span></span>

  - <span data-ttu-id="a719c-394">**Mode diagnostic**     Crée un rapport qui inclut des informations sur les tables (nombre d’enregistrements, fragmentation, taille des données et taille de l’index), tailles des fichiers de données et des fichiers journaux, dernière heure de sauvegarde, répartition des contacts entre les serveurs qui exécutent Microsoft Office Communications Server, le nombre moyen d’autorisations, de contacts, de conteneurs, d’abonnements, de publications, de points de terminaison par utilisateur, les utilisateurs mal hébergés, les utilisateurs qui ne peuvent pas être routés, le nombre moyen de conférences organisées par utilisateur, les conférences planifiées, les conférences actives et la</span><span class="sxs-lookup"><span data-stu-id="a719c-394">**Diagnostic mode**   Creates a report that includes information about tables (number of records, fragmentation, data size, and index size), data and log file sizes, the last back-up time, contact distribution among servers that are running Microsoft Office Communications Server, the average number of permissions, contacts, containers, subscriptions, publications, endpoints per user, any improperly homed users, users that can’t be routed, the average number of conferences organized per user, scheduled conferences, active conferences, and the database version.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a719c-395">L’exécution du mode diagnostic peut affecter les performances du serveur.</span><span class="sxs-lookup"><span data-stu-id="a719c-395">Running diagnostic mode can affect server performance.</span></span>

    
    </div>

  - <span data-ttu-id="a719c-396">Mode de données **utilisateur**   Signale les données de contact, de conteneur, d’abonnement, de publication, d’autorisation et de groupe de contacts pour un utilisateur spécifié ou pour les utilisateurs qui disposent de cet utilisateur dans leur liste de contacts et d’autorisations.</span><span class="sxs-lookup"><span data-stu-id="a719c-396">**User data mode**  Reports contact, container, subscription, publication, permission, and contact-group data for a specified user or for users who have that user in their contact and permission lists.</span></span> <span data-ttu-id="a719c-397">Ce mode signale également les données récapitulatives des conférences auxquelles un utilisateur est organisé ou auquel il est invité.</span><span class="sxs-lookup"><span data-stu-id="a719c-397">This mode also reports summary data for conferences that a user organizes or is invited to.</span></span>

  - <span data-ttu-id="a719c-398">**Mode conférence**     Fournit des informations détaillées sur une conférence spécifique, y compris tous les détails de l’heure de planification de la Conférence, la liste des invités, la liste des types de médias autorisés pour la Conférence, les MCU actifs (unités de contrôle multipoint), la liste des participants actifs et l’état de signalisation de chaque participant.</span><span class="sxs-lookup"><span data-stu-id="a719c-398">**Conference mode**   Reports detailed data for a specific conference, including all schedule-time details for the conference, the invitee list, the list of media types allowed for the conference, active MCUs (multipoint control units), the active participant list, and each participant’s signaling state.</span></span>

  - <span data-ttu-id="a719c-399">ID de réunion de **décodage**    Décode un ID de réunion PSTN (réseau téléphonique commuté) spécifié par le commutateur **/pstnid** , mais ne se connecte pas au serveur principal pour obtenir des informations détaillées.</span><span class="sxs-lookup"><span data-stu-id="a719c-399">**Decode Meeting ID**  Decodes a public switched telephone network (PSTN) meeting ID that is specified by the **/pstnid** switch but does not connect to the back end for detailed information.</span></span>

  - <span data-ttu-id="a719c-400">**Résoudre la Conférence**     Décode un ID de réunion PSTN spécifié par le commutateur **/pstnid** et affiche des informations sur la Conférence indiquée par l’ID.</span><span class="sxs-lookup"><span data-stu-id="a719c-400">**Resolve conference**   Decodes a PSTN meeting ID that is specified by the **/pstnid** switch and displays information about the conference indicated by the ID.</span></span>

  - <span data-ttu-id="a719c-401">**Mode MCU**    Signale l’ID, le type de média, l’URL, l’état de la pulsation, la charge de conférence et la charge des participants pour chaque MCU du pool.</span><span class="sxs-lookup"><span data-stu-id="a719c-401">**MCUs mode**  Reports the ID, media type, URL, heartbeat status, conference load, and participant load for each MCU in the pool.</span></span>

  - <span data-ttu-id="a719c-402">Mode de fragmentation de **disque**    Affiche l’état de fragmentation de tous les disques.</span><span class="sxs-lookup"><span data-stu-id="a719c-402">**Disk fragmentation mode**  Displays the fragmentation status of all disks.</span></span>

<span data-ttu-id="a719c-403">Cet outil permet de diagnostiquer divers problèmes ou d’aider les administrateurs à planifier la capacité.</span><span class="sxs-lookup"><span data-stu-id="a719c-403">This tool can be used to diagnose various problems or to assist administrators with capacity planning.</span></span> <span data-ttu-id="a719c-404">Par exemple, si la plupart des utilisateurs hébergés sur le serveur A choisissent les utilisateurs hébergés sur le serveur B comme contacts, l’administrateur peut déplacer les utilisateurs sur le serveur A vers le serveur B afin de réduire le trafic entre les serveurs.</span><span class="sxs-lookup"><span data-stu-id="a719c-404">For example, if most of the users homed on server A choose users homed on server B as their contacts, the administrator can move the users on server A to server B to reduce cross-server traffic.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="a719c-405">Output</span><span class="sxs-lookup"><span data-stu-id="a719c-405">Output</span></span>

<span data-ttu-id="a719c-406">Cet outil génère des rapports prédéfinis sur la base de données Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a719c-406">This tool outputs predefined reports about the Lync Server 2013 database.</span></span> <span data-ttu-id="a719c-407">**Chemin d’accès :** % ProgramFiles% \\ Microsoft Lync Server 2013 \\ reskit</span><span class="sxs-lookup"><span data-stu-id="a719c-407">**Path:** %ProgramFiles%\\Microsoft Lync Server 2013\\Reskit</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="a719c-408">Objectif</span><span class="sxs-lookup"><span data-stu-id="a719c-408">Purpose</span></span>

<span data-ttu-id="a719c-409">Pour installer Dbanalyze.exe, copiez-le dans un dossier local, puis exécutez l’outil.</span><span class="sxs-lookup"><span data-stu-id="a719c-409">To install Dbanalyze.exe, copy it to a local folder and then run the tool.</span></span> <span data-ttu-id="a719c-410">Pour utiliser l’outil, exécutez la commande suivante à partir de la ligne de commande.`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`</span><span class="sxs-lookup"><span data-stu-id="a719c-410">To use the tool, run the following command from the command line.`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`</span></span> <span data-ttu-id="a719c-411">Les descriptions des options de ligne de commande sont présentées ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="a719c-411">The descriptions for the command-line options are shown below.</span></span>

<span data-ttu-id="a719c-412">![Options de ligne de commande pour Dbanalyze.exe.](images/JJ945604.22bf3432-af6d-495b-8f48-d94c5d259523(OCS.15).jpg "Options de ligne de commande pour Dbanalyze.exe.")</span><span class="sxs-lookup"><span data-stu-id="a719c-412">![Command line options for Dbanalyze.exe.](images/JJ945604.22bf3432-af6d-495b-8f48-d94c5d259523(OCS.15).jpg "Command line options for Dbanalyze.exe.")</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="a719c-413">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="a719c-413">Requirements</span></span>

<span data-ttu-id="a719c-414">**Ordinateur** DBAnalyze ne peut être exécuté qu’à partir d’un ordinateur joint à un domaine sur lequel Lync Server 2013 est installé.</span><span class="sxs-lookup"><span data-stu-id="a719c-414">**Computer** DBAnalyze can be run only from a domain-joined computer that has Lync Server 2013 installed.</span></span>

<span data-ttu-id="a719c-415">**Réseau** L’ordinateur doit être en mesure de se connecter à la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="a719c-415">**Network** The computer should be able to connect to the back-end database.</span></span>

<span data-ttu-id="a719c-416">**Logiciels** Les composants logiciels Lync Server 2013 doivent être installés avant d’exécuter DBAnalyze.</span><span class="sxs-lookup"><span data-stu-id="a719c-416">**Software** Lync Server 2013 software components must be installed before running DBAnalyze.</span></span>

<span data-ttu-id="a719c-417">**Les utilisateurs** Le tableau ci-dessous montre les administrateurs qui disposent des autorisations nécessaires pour accéder aux bases de données Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a719c-417">**Users**The table below shows the administrators who have the necessary permissions to access Lync Server 2013 databases.</span></span>

<span data-ttu-id="a719c-418">![Tableau des autorisations pour Dbanalyze.exe.](images/JJ945604.b8931e9e-834e-4dec-8a84-2fc47d1613e9(OCS.15).jpg "Tableau des autorisations pour Dbanalyze.exe.")</span><span class="sxs-lookup"><span data-stu-id="a719c-418">![Permissions table for Dbanalyze.exe.](images/JJ945604.b8931e9e-834e-4dec-8a84-2fc47d1613e9(OCS.15).jpg "Permissions table for Dbanalyze.exe.")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a719c-419">Un compte d’administrateur local est requis pour le mode <STRONG>/Report : Disk</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="a719c-419">A local administrator account is required for <STRONG>/report:disk</STRONG> mode.</span></span>



</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="a719c-420">Exemples</span><span class="sxs-lookup"><span data-stu-id="a719c-420">Examples</span></span>

<span data-ttu-id="a719c-421">Voici des exemples de commandes Dbanalyze.exe valides :</span><span class="sxs-lookup"><span data-stu-id="a719c-421">The following are examples of valid Dbanalyze.exe commands:</span></span>

    dbanalyze.exe /report:diag
    dbanalyze.exe /report:user /user:usera@domainb.com
    dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
    dbanalyze.exe /report:resolve /pstnid:12345
    dbanalyze.exe /report:mcus
    dbanalyze.exe /report:disk

</div>

<div>

## <a name="summary"></a><span data-ttu-id="a719c-422">Résumé</span><span class="sxs-lookup"><span data-stu-id="a719c-422">Summary</span></span>

<span data-ttu-id="a719c-423">DBAnalyzer fournit aux administrateurs un moyen rapide et simple d’analyser les bases de données Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a719c-423">DBAnalyzer provides administrators a quick and easy to analyze Lync Server 2013 databases.</span></span>

</div>

</div>

<div>

## <a name="importstorageservicedata"></a><span data-ttu-id="a719c-424">ImportStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="a719c-424">ImportStorageServiceData</span></span>

<span data-ttu-id="a719c-425">L’outil Kit de ressources ImportStorageServiceData permet de réimporter les données de point de terminaison et de file d’attente qui ont été vidées du service de stockage (LYSS) dans le service de stockage.</span><span class="sxs-lookup"><span data-stu-id="a719c-425">The ImportStorageServiceData resource kit tool allows for re-importing Queue and Endpoint data that was flushed out of the Storage Service (LYSS) back into the Storage Service.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="a719c-426">Description</span><span class="sxs-lookup"><span data-stu-id="a719c-426">Description</span></span>

<span data-ttu-id="a719c-427">Les données vidées du service de stockage ont pu être automatiques (périodiques) en fonction de l’état des éléments de file d’attente ou de la taille de la base de données.</span><span class="sxs-lookup"><span data-stu-id="a719c-427">The data flushed out of the Storage Service could have been automatic (periodic) based on Queue Item status or database size.</span></span> <span data-ttu-id="a719c-428">Cela peut être dû à l’invocation manuelle de la cmdlet de basculement du pool ou à la cmdlet StorageServiceFullFlush (appelée par l’applet de commande de basculement du pool).</span><span class="sxs-lookup"><span data-stu-id="a719c-428">It could have happened due to the manual invocation of the pool failover cmdlet, or the StorageServiceFullFlush cmdlet (which the pool failover cmdlet invokes).</span></span> <span data-ttu-id="a719c-429">Notez que les données ne doivent idéalement pas être réimportées si l’une des bases de données du service de stockage (LYSS) sur les serveurs frontaux se trouve au-dessus du niveau normal, car cela entraînera probablement une plus grande exportation des données. De plus, tous les problèmes susceptibles d’avoir contribué à l’augmentation de la file d’attente du service de stockage doivent d’abord être résolus (par exemple, des erreurs de point de terminaison Exchange, des problèmes réseau ou d’autres problèmes).</span><span class="sxs-lookup"><span data-stu-id="a719c-429">Note that data should ideally not be re-imported if any of the Storage Service (LYSS ) database size on the front ends is above the normal level, because doing so will likely just cause more data to be exported back out. Furthermore, any problems which could have contributed to errors that caused the Storage Service Queue to grow should first be resolved (for example Exchange endpoint errors, network issues, or other problems).</span></span>

<span data-ttu-id="a719c-430">**Scénario 1 :** lors du basculement de pool, les fichiers peuvent être vidés du service de stockage pour chaque serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="a719c-430">**Scenario 1:** during pool failover, files may be flushed out from storage service for each front end.</span></span> <span data-ttu-id="a719c-431">Une fois le basculement terminé, l’outil doit être exécuté pour réimporter les données.</span><span class="sxs-lookup"><span data-stu-id="a719c-431">After failover is completed, the tool should be run to re-import the data.</span></span>

<span data-ttu-id="a719c-432">**Scénario 2 :** les données sont vidées automatiquement chaque jour ou en réponse à une base de données de service de stockage dépassant certains seuils de taille (par exemple 60%, 80%, 90% complet).</span><span class="sxs-lookup"><span data-stu-id="a719c-432">**Scenario 2:** data is being flushed automatically each day or in response to Storage Service database exceeding certain size thresholds ( for example 60%, 80%, 90% full ).</span></span> <span data-ttu-id="a719c-433">Les données vidées automatiquement doivent être régulièrement réimportées par l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="a719c-433">This automatically flushed data should be re-imported routinely by the administrator.</span></span> <span data-ttu-id="a719c-434">Dans la situation ci-dessus, si le Pack SCOM de surveillance n’est pas déployé, il existe des événements pour le service de stockage Lync Server concernant les données vidées du service de stockage.</span><span class="sxs-lookup"><span data-stu-id="a719c-434">In the above situation, if the monitoring SCOM pack is not deployed, there are events for Lync Server Storage Service relating to data being flushed from the Storage Service.</span></span> <span data-ttu-id="a719c-435">Les ID d’événement de 32075 (opération de vidage complète est démarré), 32076 (vidage complet terminé), 32082 (maintenance de niveau de maintenance démarré), 32083 (vidage du niveau de maintenance terminé), 32089 (vidage dû à la fin de la base de données).</span><span class="sxs-lookup"><span data-stu-id="a719c-435">Event IDs of 32075 (full flush operation is started), 32076 (full flush has completed), 32082 (maintenance level flush started), 32083 (maintenance level flush complete), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="a719c-436">Remarque ces ID d’événement correspondent à la version RTM.</span><span class="sxs-lookup"><span data-stu-id="a719c-436">Note these event Ids correspond to the RTM release.</span></span> <span data-ttu-id="a719c-437">Lorsqu’un administrateur voit ces événements, cela signifie qu’il existe des fichiers qui ont été vidés. Ces données doivent régulièrement être importées à l’aide de cet outil, par exemple une fois par semaine.</span><span class="sxs-lookup"><span data-stu-id="a719c-437">When an administrator sees these events, it means that there are files that have been flushed out. This data should routinely be imported back using this tool, for example once per week.</span></span>

<span data-ttu-id="a719c-438">Pour la version de service en ligne, si le Pack SCOM à analyse d’intégrité pour Lync Server est déployé, il existe de nouvelles alertes pouvant être déclenchées, qui demandent à l’administrateur de réimporter les données vidées dans le service de stockage.</span><span class="sxs-lookup"><span data-stu-id="a719c-438">For the Online Service release, if health monitoring SCOM pack for Lync Server is deployed, there are new alerts which may be raised which ask the administrator to re-import the flushed data back into Storage Service.</span></span> <span data-ttu-id="a719c-439">Il y aura un événement correspondant dans le journal des événements sur le serveur frontal qui a déclenché l’alerte.</span><span class="sxs-lookup"><span data-stu-id="a719c-439">There will be a corresponding event in the event log on the Front End server which triggered the alert.</span></span> <span data-ttu-id="a719c-440">L’événement fournira une description du chemin d’accès parent sous lequel se trouvent les fichiers de données vidés, ainsi que le nombre de fichiers correspondant aux critères d’alerte.</span><span class="sxs-lookup"><span data-stu-id="a719c-440">The event will give a description of the Parent path under which the flushed data files are located, as well as how many files there are which meet the alert criteria.</span></span> <span data-ttu-id="a719c-441">Le critère d’alerte est qu’il y a des fichiers X ou plus sous le chemin d’accès parent en particulier dont la version est d’au moins Y jours (où X et Y sont prédéfinis dans le StorageService, mais qui peuvent être remplacés en modifiant le fichier APPCONFIG.) Deux exemples d’événements pouvant déclencher l’alerte d’intégrité sont indiqués ci-dessous, la différence étant le chemin d’accès parent.</span><span class="sxs-lookup"><span data-stu-id="a719c-441">The alert criteria is that there are X or more files under the particular parent path which are at least Y days old ( where X and Y are preset within the StorageService but can be overridden by changing the APPCONFIG file.)Two examples of events which can trigger the health alert are shown below, with the difference being their parent path.</span></span> <span data-ttu-id="a719c-442">Une possibilité se trouve sous le partage de fichiers de service Web, tandis que l’autre peut être le répertoire de données d’application local de chaque serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="a719c-442">One possibility is under Web service file share, while the other possibility is the local Application Data directory of each front end.</span></span> <span data-ttu-id="a719c-443">(par exemple c : \\ ProgramData \\ Microsoft \\ Lync Server \\ StorageService).</span><span class="sxs-lookup"><span data-stu-id="a719c-443">( for example c:\\ProgramData\\Microsoft\\Lync Server\\StorageService ).</span></span> <span data-ttu-id="a719c-444">L’administrateur exécutera ensuite cet outil reskit.</span><span class="sxs-lookup"><span data-stu-id="a719c-444">The administrator will then run this reskit tool.</span></span>

<span data-ttu-id="a719c-445">Cet outil augmentera la charge d’UC et d’e/s sur le serveur frontal sur lequel il est exécuté, ainsi que d’autres serveurs frontaux, dans la situation où les données ne sont pas détenues par le serveur frontal sur lequel l’outil est exécuté.</span><span class="sxs-lookup"><span data-stu-id="a719c-445">This tool will increase CPU and IO load on the front end it is running on, as well as other front ends, in the situation that the data is not owned by the front end that the tool is executed on.</span></span> <span data-ttu-id="a719c-446">Nous vous recommandons d’exécuter cet outil lorsque les serveurs frontaux ne sont pas fortement sollicités par le processeur et la charge d’e/s, par exemple en dehors des heures de pointe.</span><span class="sxs-lookup"><span data-stu-id="a719c-446">We recommend runng this tool when front ends are not under heavy CPU and IO load, for example outside of peak hours.</span></span> <span data-ttu-id="a719c-447">Deuxièmement, cet outil peut 2 à 3 minutes pour importer un fichier de données.</span><span class="sxs-lookup"><span data-stu-id="a719c-447">Secondly, this tool can 2 to 3 minutes to import one data file.</span></span> <span data-ttu-id="a719c-448">Gardez cela à l’esprit lorsque vous évaluez la durée d’exécution de l’outil. Le fichier journal détaillé généré par l’outil apparaît par défaut sur le magasin de fichiers.</span><span class="sxs-lookup"><span data-stu-id="a719c-448">Keep this in mind when estimating how long tool will be running.The verbose log file generated by the tool will by default appear on the File Store.</span></span> <span data-ttu-id="a719c-449">Supprimez-le s’il n’y a aucune erreur signalée, car le fichier journal peut utiliser des dizaines de Mo ou plus.</span><span class="sxs-lookup"><span data-stu-id="a719c-449">Delete it if there are no errors reported, because the log file can be tens of MB or more.</span></span>

<span data-ttu-id="a719c-450">![Exemples d’événements du journal des événements du serveur de stockage.](images/JJ945604.3a903ef7-ea8a-4606-8229-a3e32f13af3a(OCS.15).jpg "Exemples d’événements du journal des événements du serveur de stockage.")</span><span class="sxs-lookup"><span data-stu-id="a719c-450">![Sample Storage Server event log events.](images/JJ945604.3a903ef7-ea8a-4606-8229-a3e32f13af3a(OCS.15).jpg "Sample Storage Server event log events.")</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="a719c-451">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="a719c-451">Requirements</span></span>

<span data-ttu-id="a719c-452">Installez les outils du kit de ressources Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a719c-452">Install the Lync Server 2013, Resource Kit Tools.</span></span> <span data-ttu-id="a719c-453">L’outil s’exécute sur des ordinateurs liés à un domaine sur lesquels Lync Server et Lync Server Management Shell sont installés.</span><span class="sxs-lookup"><span data-stu-id="a719c-453">The tool runs on domain-joined machines where Lync Server and Lync Server Management Shell are installed.</span></span> <span data-ttu-id="a719c-454">L’outil utilise une cmdlet de Management Shell pour identifier tous les serveurs frontaux du pool.</span><span class="sxs-lookup"><span data-stu-id="a719c-454">The tool uses a cmdlet from the management shell to identify all the Front End servers in the pool.</span></span> <span data-ttu-id="a719c-455">Deuxièmement, l’outil doit être exécuté à partir d’un ordinateur du pool sur lequel la base de données **RtcLocal** est installée.</span><span class="sxs-lookup"><span data-stu-id="a719c-455">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="a719c-456">Cette base de données est utilisée par l’outil pour récupérer l’emplacement du partage de fichiers WebService pour le pool. De plus, avant d’utiliser l’outil, chaque serveur frontal doit d’abord activer la communication à distance Windows PowerShell à l’aide de **Enable-PSRemoting** sur chaque serveur frontal, ainsi que la machine à partir de laquelle l’outil est exécuté.</span><span class="sxs-lookup"><span data-stu-id="a719c-456">This database is used by the tool to retrieve the location of the WEBSERVICE file share for the pool.Additionally, before using the tool, each Front End server must first enable Windows PowerShell Remoting using **Enable-PSRemoting** on each Front End server, as well as the machine that the tool is executed from.</span></span> <span data-ttu-id="a719c-457">Dans le cas contraire, les commandes Windows PowerShell distantes à partir de cet outil échoueront.</span><span class="sxs-lookup"><span data-stu-id="a719c-457">Otherwise, remote Windows PowerShell commands from this tool will fail.</span></span> <span data-ttu-id="a719c-458">La communication à distance Windows PowerShell peut être désactivée sur tous les serveurs frontaux du pool une fois terminé.</span><span class="sxs-lookup"><span data-stu-id="a719c-458">Windows PowerShell Remoting can be turned off on all Front End servers in the pool after it is finished.</span></span> <span data-ttu-id="a719c-459">Enfin, le compte ou les informations d’identification appelant l’outil doivent disposer d’une autorisation en lecture/écriture sur le partage de fichiers WebPart pour le pool sur lequel ils exécutent cet outil.</span><span class="sxs-lookup"><span data-stu-id="a719c-459">Finally, the account or credential invoking the tool must have read/write permission to the webservice file share for the pool they are executing this tool on.</span></span> <span data-ttu-id="a719c-460">Dans le cas contraire, l’outil échoue avec des erreurs d’autorisation d’e/s.</span><span class="sxs-lookup"><span data-stu-id="a719c-460">Otherwise the tool will fail with IO Permission errors.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a719c-461">Sur Windows Server 2012, la communication à distance Windows PowerShell est activée par défaut, mais pas avec le système d’exploitation Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="a719c-461">On Windows Server 2012, Windows PowerShell Remoting is enabled by default, but not on the Windows Server 2008 operating system.</span></span>



</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="a719c-462">Exemples</span><span class="sxs-lookup"><span data-stu-id="a719c-462">Examples</span></span>

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

</div>

</div>

<div>

## <a name="lcssync"></a><span data-ttu-id="a719c-463">LCSSync</span><span class="sxs-lookup"><span data-stu-id="a719c-463">LCSSync</span></span>

<span data-ttu-id="a719c-464">L’outil LCSSync permet de déployer le logiciel de communication Lync Server 2013 dans un environnement à forêts multiples.</span><span class="sxs-lookup"><span data-stu-id="a719c-464">The LCSSync tool helps to deploy Lync Server 2013 communications software in a multi-forest environment.</span></span> <span data-ttu-id="a719c-465">Cet outil permet de synchroniser les utilisateurs et les groupes de différentes forêts d’utilisateurs en tant qu’objet de contact des services de domaine Active Directory avec une forêt centrale où Lync Server 2013 est installé.</span><span class="sxs-lookup"><span data-stu-id="a719c-465">This tool is used to synchronize users and groups from different user forests as an Active Directory Domain Services contact object to a central forest where Lync Server 2013 is installed.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="a719c-466">Description</span><span class="sxs-lookup"><span data-stu-id="a719c-466">Description</span></span>

<span data-ttu-id="a719c-467">LCSSync utilise les objets de contact des services de domaine Active Directory synchronisés dans la forêt centrale pour activer les utilisateurs pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a719c-467">LCSSync uses the synchronized Active Directory Domain Services contact objects in the central forest to enable users for Lync Server.</span></span> <span data-ttu-id="a719c-468">Pour fournir une connexion unique, le compte d’utilisateur principal doit être mappé à l’objet contact des services de domaine Active Directory dans la forêt centrale pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a719c-468">To provide single sign-in, the primary user account must be mapped to the Active Directory Domain Services contact object in the central forest for Lync Server 2013.</span></span> <span data-ttu-id="a719c-469">Cet outil permet d’effectuer ce mappage.</span><span class="sxs-lookup"><span data-stu-id="a719c-469">This tool helps perform that mapping.</span></span> <span data-ttu-id="a719c-470">Cet outil fournit des modèles pour la création d’agents de gestion dans le serveur Microsoft Identity Integration Server.</span><span class="sxs-lookup"><span data-stu-id="a719c-470">This tool provides templates for creating Management Agents in the Microsoft Identity Integration Server.</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="a719c-471">Résumé</span><span class="sxs-lookup"><span data-stu-id="a719c-471">Summary</span></span>

<span data-ttu-id="a719c-472">L’outil LCSSync permet de déployer Lync Server dans un environnement à forêts multiples.</span><span class="sxs-lookup"><span data-stu-id="a719c-472">The LCSSync tool helps to deploy Lync Server in a multi-forest environment.</span></span>

</div>

</div>

<div>

## <a name="lookupuserconsole"></a><span data-ttu-id="a719c-473">LookupUserConsole</span><span class="sxs-lookup"><span data-stu-id="a719c-473">LookupUserConsole</span></span>

<span data-ttu-id="a719c-474">L’outil LookupUserConsole affiche des informations de routage Lync Server internes sur des utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="a719c-474">The LookupUserConsole tool displays internal Lync Server routing information about specific users.</span></span> <span data-ttu-id="a719c-475">Ces informations peuvent être utiles au support technique de Microsoft pour diagnostiquer les problèmes de déploiement et de routage.</span><span class="sxs-lookup"><span data-stu-id="a719c-475">This information may be useful to Microsoft support personal in diagnosing deployment and routing problems.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="a719c-476">Description</span><span class="sxs-lookup"><span data-stu-id="a719c-476">Description</span></span>

<span data-ttu-id="a719c-477">L’exécution d' LookupUserConsole.exe ouvre une invite de commandes qui accepte les adresses SIP et tente d’afficher les informations de routage internes de Lync Server qui les concernent.</span><span class="sxs-lookup"><span data-stu-id="a719c-477">Executing LookupUserConsole.exe will open a command prompt that accepts SIP addresses and attempts to display internal Lync Server routing information relating them.</span></span> <span data-ttu-id="a719c-478">Tapez **Exit** pour quitter l’outil LookupUserConsole.</span><span class="sxs-lookup"><span data-stu-id="a719c-478">Type **exit** to quit the LookupUserConsole tool.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="a719c-479">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="a719c-479">Requirements</span></span>

<span data-ttu-id="a719c-480">Installez les outils du kit de ressources Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a719c-480">Install the Lync Server 2013, Resource Kit Tools.</span></span> <span data-ttu-id="a719c-481">L’outil s’exécute sur des ordinateurs liés à un domaine sur lesquels Lync Server est installé</span><span class="sxs-lookup"><span data-stu-id="a719c-481">The tool runs on domain-joined machines where Lync Server is installed</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="a719c-482">Exemples</span><span class="sxs-lookup"><span data-stu-id="a719c-482">Examples</span></span>

<span data-ttu-id="a719c-483">C : \\ Program Files \\ Microsoft Lync Server 2013 \\ reskit \>LookupUserConsole.exe</span><span class="sxs-lookup"><span data-stu-id="a719c-483">C:\\Program Files\\Microsoft Lync Server 2013\\ResKit\>LookupUserConsole.exe</span></span>

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

</div>

</div>

<div>

## <a name="msturnping"></a><span data-ttu-id="a719c-484">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="a719c-484">MsTurnPing</span></span>

<span data-ttu-id="a719c-485">L’outil MSTurnPing permet à un administrateur du logiciel de communications Microsoft Lync Server 2013 de vérifier l’état des serveurs exécutant les services d’authentification audio/vidéo et audio/vidéo, ainsi que les serveurs qui exécutent les services de stratégie de bande passante dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="a719c-485">The MSTurnPing tool allows an administrator of Microsoft Lync Server 2013 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="a719c-486">Description</span><span class="sxs-lookup"><span data-stu-id="a719c-486">Description</span></span>

<span data-ttu-id="a719c-487">L’outil MSTurnPing permet à un administrateur du logiciel de communication Lync Server 2013 de vérifier l’état des serveurs exécutant les services d’authentification audio/vidéo et audio/vidéo, ainsi que les serveurs qui exécutent des services de stratégie de bande passante dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="a719c-487">The MSTurnPing tool allows an administrator of Lync Server 2013 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

<span data-ttu-id="a719c-488">L’outil permet à l’administrateur d’effectuer les tests suivants :</span><span class="sxs-lookup"><span data-stu-id="a719c-488">The tool allows the administrator to perform the following tests:</span></span>

1.  <span data-ttu-id="a719c-489">Test du serveur Edge a/V : l’outil effectue des tests sur tous les serveurs Edge A/V de la topologie en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="a719c-489">A/V Edge Server test: The tool performs tests against all A/V Edge Servers in the topology by doing the following:</span></span>
    
      - <span data-ttu-id="a719c-490">Vérification que le service d’authentification audio/vidéo de Lync Server est démarré et peut émettre des informations d’identification correctes.</span><span class="sxs-lookup"><span data-stu-id="a719c-490">Verifying that the Lync Server Audio/Video Authentication service is started and can issue proper credentials.</span></span>
    
      - <span data-ttu-id="a719c-491">Vérification que le service Edge audio/vidéo de Lync Server est démarré et peut allouer correctement les ressources sur le serveur Edge externe.</span><span class="sxs-lookup"><span data-stu-id="a719c-491">Verifying that the Lync Server Audio/Video Edge service is started and can allocate the resources on the external edge successfully.</span></span>

2.  <span data-ttu-id="a719c-492">Test du service de stratégie de bande passante : l’outil effectue des tests sur tous les serveurs qui exécutent les services de stratégie de bande passante dans la topologie en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="a719c-492">Bandwidth Policy Service test: The tool performs tests against all the servers that are running the Bandwidth Policy Services in the topology by doing the following:</span></span>
    
      - <span data-ttu-id="a719c-493">Vérifier que le service de stratégie de bande passante Lync Server (authentification) est démarré et peut émettre des informations d’identification appropriées.</span><span class="sxs-lookup"><span data-stu-id="a719c-493">Verifying that the Lync Server Bandwidth Policy Service (Authentication) is started and can issue proper credentials.</span></span>
    
      - <span data-ttu-id="a719c-494">Vérification que le service de stratégie de bande passante Lync Server (Core) est démarré et peut effectuer la vérification de bande passante.</span><span class="sxs-lookup"><span data-stu-id="a719c-494">Verifying that the Lync Server Bandwidth Policy Service (Core) is started and can perform the bandwidth check successfully.</span></span>

<span data-ttu-id="a719c-495">Cet outil doit être exécuté à partir d’un ordinateur qui fait partie de la topologie et sur lequel le magasin local est installé.</span><span class="sxs-lookup"><span data-stu-id="a719c-495">This tool must be run from a computer that is part of the topology and has the local store installed.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="a719c-496">Output</span><span class="sxs-lookup"><span data-stu-id="a719c-496">Output</span></span>

<span data-ttu-id="a719c-497">L’outil renvoie les résultats de chacune des opérations.</span><span class="sxs-lookup"><span data-stu-id="a719c-497">The tool outputs the results of each of the operations.</span></span>

  - <span data-ttu-id="a719c-498">Si le test **AudioVideoEdgeServer** est effectué, les sorties de l’outil sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="a719c-498">If the **AudioVideoEdgeServer** test is performed, the tool outputs are the following:</span></span>
    
      - <span data-ttu-id="a719c-499">Les résultats des tests des ordinateurs qui fournissent le service d’authentification audio/vidéo Lync Server dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="a719c-499">The test results of the computers that provide the Lync Server Audio/Video Authentication service in the topology</span></span>
    
      - <span data-ttu-id="a719c-500">Les résultats des tests des ordinateurs qui fournissent le service Edge audio/vidéo Lync Server dans la topologie</span><span class="sxs-lookup"><span data-stu-id="a719c-500">The test results of the computers that provide the Lync Server Audio/Video Edge service in the topology</span></span>

  - <span data-ttu-id="a719c-501">Si le test **BandwidthPolicyServer** est effectué, les sorties de l’outil sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="a719c-501">If the **BandwidthPolicyServer** test is performed, the tool outputs are the following:</span></span>
    
      - <span data-ttu-id="a719c-502">Les résultats des tests des ordinateurs qui fournissent le service de stratégie de bande passante Lync Server (authentification) dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="a719c-502">The test results of the computers that provide the Lync Server Bandwidth Policy Service (Authentication) in the topology</span></span>
    
      - <span data-ttu-id="a719c-503">Les résultats des tests des ordinateurs qui fournissent le service de stratégie de bande passante Lync Server (Core) dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="a719c-503">The test results of the computers that provide the Lync Server Bandwidth Policy Service (Core) in the topology</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="a719c-504">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="a719c-504">Requirements</span></span>

  - <span data-ttu-id="a719c-505">Cet outil doit être exécuté à partir d’un ordinateur qui se trouve dans la topologie et qui a le magasin local.</span><span class="sxs-lookup"><span data-stu-id="a719c-505">This tool must be run from a computer that is in the topology and that has the local store.</span></span>

  - <span data-ttu-id="a719c-506">L’outil doit être exécuté en tant qu’administrateur ayant accès au magasin local.</span><span class="sxs-lookup"><span data-stu-id="a719c-506">The tool must be run as an administrator who has access to the local store.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="a719c-507">Exemples</span><span class="sxs-lookup"><span data-stu-id="a719c-507">Examples</span></span>

<span data-ttu-id="a719c-508">Voici un exemple de l’entrée d’outil.</span><span class="sxs-lookup"><span data-stu-id="a719c-508">The following is an example of the tool input.</span></span>

    MsTurnPing -ServerRole AudioVideoEdgeServer
    
    MsTurnPing -ServerRole BandwidthPolicyServer

</div>

<div>

## <a name="summary"></a><span data-ttu-id="a719c-509">Résumé</span><span class="sxs-lookup"><span data-stu-id="a719c-509">Summary</span></span>

<span data-ttu-id="a719c-510">Cet outil peut être une ressource précieuse pour les administrateurs Lync Server 2013 qui souhaitent vérifier l’état des serveurs qui exécutent les services de stratégie de bande passante et audio/vidéo.</span><span class="sxs-lookup"><span data-stu-id="a719c-510">This tool can be a valuable resource to Lync Server 2013 administrators who want to check the status of the servers that are running audio/video and bandwidth policy services.</span></span>

</div>

</div>

<div>

## <a name="network-configuration-viewer"></a><span data-ttu-id="a719c-511">Afficheur de configuration réseau</span><span class="sxs-lookup"><span data-stu-id="a719c-511">Network Configuration Viewer</span></span>

<span data-ttu-id="a719c-512">La visionneuse de configuration réseau peut être utilisée par les administrateurs de logiciels de communication Microsoft Lync Server 2013 pour afficher la topologie réseau CAC (Call Admission Control) pour une entreprise qui est configurée pour autoriser les sessions de communication en temps réel, telles que les appels vocaux ou vidéo en fonction de la capacité de bande passante spécifiée.</span><span class="sxs-lookup"><span data-stu-id="a719c-512">Network Configuration Viewer can be used by Microsoft Lync Server 2013 communications software administrators to view call admission control (CAC) network topology for an enterprise that is provisioned to allow real-time communication sessions, such as voice or video calls based on specified bandwidth capacity.</span></span> <span data-ttu-id="a719c-513">Les administrateurs de Lync Server 2013 définissent les stratégies de contrôle d’admission des stratégies qui sont appliquées par les services de stratégie de bande passante installés avec Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a719c-513">Lync Server 2013 administrators define CAC policies, which are enforced by the Bandwidth Policy services that are installed with Lync Server 2013.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="a719c-514">Description</span><span class="sxs-lookup"><span data-stu-id="a719c-514">Description</span></span>

<span data-ttu-id="a719c-515">La visionneuse de configuration réseau (NetworkConfigurationViewer.exe) permet aux administrateurs d’effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="a719c-515">Network Configuration Viewer (NetworkConfigurationViewer.exe) allows administrators to perform the following tasks:</span></span>

  - <span data-ttu-id="a719c-516">Chargez et affichez la topologie de réseau CAC à partir d’un déploiement Lync Server 2013 dans un format graphique.</span><span class="sxs-lookup"><span data-stu-id="a719c-516">Load and view CAC network topology from a Lync Server 2013 deployment in a graphical format.</span></span>

  - <span data-ttu-id="a719c-517">Chargez et affichez la topologie de réseau CAC à partir d’un fichier journal de serveur de stratégie de bande passante dans un format graphique.</span><span class="sxs-lookup"><span data-stu-id="a719c-517">Load and view CAC network topology from a Bandwidth Policy Server log file in a graphical format.</span></span>

  - <span data-ttu-id="a719c-518">Enregistrez et stockez la topologie de réseau CAC au format XML sur le disque.</span><span class="sxs-lookup"><span data-stu-id="a719c-518">Save and store CAC network topology in an XML format on the disk.</span></span>

  - <span data-ttu-id="a719c-519">Enregistrer et stocker le diagramme de topologie réseau CAC au format JPG ou BMP.</span><span class="sxs-lookup"><span data-stu-id="a719c-519">Save and store CAC network topology diagram in JPG or BMP format.</span></span>

  - <span data-ttu-id="a719c-520">Afficher les données de configuration de la topologie réseau CAC.</span><span class="sxs-lookup"><span data-stu-id="a719c-520">View CAC network topology configuration data.</span></span>

  - <span data-ttu-id="a719c-521">Afficher la topologie du réseau CAC sous la forme d’un style d’affichage arborescent.</span><span class="sxs-lookup"><span data-stu-id="a719c-521">View CAC network topology in a tree-view style.</span></span>

  - <span data-ttu-id="a719c-522">Définissez des connecteurs personnalisés pour les liens de topologie de réseau CAC (par exemple, liaisons de site à région, de région à région et de site à site).</span><span class="sxs-lookup"><span data-stu-id="a719c-522">Define custom connectors for CAC network topology links (for example, site-to-region, region-to-region, and site-to-site links).</span></span>

  - <span data-ttu-id="a719c-523">Afficher les informations de site, les informations de région et les stratégies de bande passante et les liaisons réseau configurées pour la topologie du réseau CAC.</span><span class="sxs-lookup"><span data-stu-id="a719c-523">View CAC network topology site information, region Information, and provisioned bandwidth policies and network links.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="a719c-524">Objectif</span><span class="sxs-lookup"><span data-stu-id="a719c-524">Purpose</span></span>

<span data-ttu-id="a719c-525">Afficher les liens de topologie du réseau CAC d’entreprise dans une interface graphique.</span><span class="sxs-lookup"><span data-stu-id="a719c-525">View enterprise CAC network topology links in a graphical interface.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="a719c-526">Exemples</span><span class="sxs-lookup"><span data-stu-id="a719c-526">Examples</span></span>

<span data-ttu-id="a719c-527">**Chargez et affichez la topologie de réseau CAC à partir d’un déploiement Lync Server 2013 dans un format graphique :** Les administrateurs Lync Server 2013 peuvent charger et afficher la configuration de la topologie du réseau CAC sur n’importe quel ordinateur Lync Server 2013 à l’aide de l’option **Télécharger la configuration réseau** , comme illustré dans la figure ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="a719c-527">**Load and view CAC network topology from a Lync Server 2013 deployment in a graphical format:** Lync Server 2013 administrators can load and view CAC network topology configuration on any Lync Server 2013 computer by using the **Download Network Configuration** option as shown in the figure below.</span></span> <span data-ttu-id="a719c-528">L’outil ne parviendra pas à télécharger ou à afficher une configuration de ce type lorsqu’il est déployé sur un ordinateur qui n’a pas de connectivité avec le magasin de configurations Lync.</span><span class="sxs-lookup"><span data-stu-id="a719c-528">The tool will fail to download or view such a configuration when deployed on a computer that does not have connectivity to the Lync configuration store.</span></span>

<span data-ttu-id="a719c-529">![Téléchargement de la configuration réseau.](images/JJ945604.8d126d3f-2545-4f13-a244-974f09614982(OCS.15).jpg "Téléchargement de la configuration réseau.")</span><span class="sxs-lookup"><span data-stu-id="a719c-529">![Downloading the network configuration.](images/JJ945604.8d126d3f-2545-4f13-a244-974f09614982(OCS.15).jpg "Downloading the network configuration.")</span></span>

<span data-ttu-id="a719c-530">**Chargez et affichez la topologie de réseau CAC à partir d’un fichier journal de serveur de stratégie de bande passante dans un format graphique :** Les serveurs de stratégie de bande passante Lync Server 2013 enregistrent la topologie de réseau CAC dans le cadre du mécanisme de journalisation sous l’emplacement de partage de fichiers de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a719c-530">**Load and View CAC network topology from a Bandwidth Policy server log file in a graphical format:** Lync Server 2013 Bandwidth Policy servers save the CAC network topology as a part of the logging mechanism under the Lync Server 2013 file share location.</span></span> <span data-ttu-id="a719c-531">Les administrateurs Lync Server peuvent afficher ce type de fichier dans un format graphique à l’aide de l’option **ouvrir la configuration du réseau** , comme indiqué ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="a719c-531">Lync Server administrators can view such a file in a graphical format by using the **Open Network Configuration** option as shown below.</span></span>

<span data-ttu-id="a719c-532">![Ouverture d’un fichier journal du serveur de stratégie de bande passante.](images/JJ945604.3e503e92-aacb-4921-a8d2-23f860fe2df6(OCS.15).jpg "Ouverture d’un fichier journal du serveur de stratégie de bande passante.")</span><span class="sxs-lookup"><span data-stu-id="a719c-532">![Opening a Bandwidth Policy Server log file.](images/JJ945604.3e503e92-aacb-4921-a8d2-23f860fe2df6(OCS.15).jpg "Opening a Bandwidth Policy Server log file.")</span></span>

<span data-ttu-id="a719c-533">Enregistrer et stocker la topologie de réseau CAC au format XML sur le disque : les administrateurs Lync Server 2013 peuvent enregistrer le fichier de configuration de la topologie réseau CAC au format XML à l’aide de l’option **enregistrer une copie de la configuration réseau** , comme indiqué ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="a719c-533">Save and store CAC network topology in an XML format on the disk: Lync Server 2013 administrators can save the CAC network topology configuration file in an XML format by using the **Save a copy of Network Configuration** option as shown below.</span></span> <span data-ttu-id="a719c-534">Le fichier de configuration enregistré peut ensuite être utilisé hors connexion à des fins d’affichage graphique.</span><span class="sxs-lookup"><span data-stu-id="a719c-534">The saved configuration file can then be used offline for graphical viewing purposes.</span></span>

<span data-ttu-id="a719c-535">![Enregistrement de la configuration réseau sous forme de fichier XML.](images/JJ945604.6eeef3b0-78b5-4ee6-8d94-1a4ddf3d8676(OCS.15).jpg "Enregistrement de la configuration réseau sous forme de fichier XML.")</span><span class="sxs-lookup"><span data-stu-id="a719c-535">![Saving the network configuration as an XML file.](images/JJ945604.6eeef3b0-78b5-4ee6-8d94-1a4ddf3d8676(OCS.15).jpg "Saving the network configuration as an XML file.")</span></span>

<span data-ttu-id="a719c-536">Enregistrer et stocker le diagramme de topologie réseau CAC au format JPG ou BMP : les administrateurs Lync Server 2013 peuvent enregistrer la configuration de la topologie du réseau CAC dans un format graphique (formats de fichiers JPG et BMP) à l’aide de l’option **enregistrer le diagramme de configuration réseau en tant qu’image** , comme illustré ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="a719c-536">Save and Store CAC network topology diagram in JPG or BMP format: Lync Server 2013 administrators can save the CAC network topology configuration in a graphical format (JPG and BMP file formats) by using the **Save Network Configuration diagram as picture** option as shown below.</span></span>

<span data-ttu-id="a719c-537">![Enregistrement de la configuration réseau en tant qu’image.](images/JJ945604.145a6fb9-58b1-46b1-bbd5-a661ceba07b4(OCS.15).jpg "Enregistrement de la configuration réseau en tant qu’image.")</span><span class="sxs-lookup"><span data-stu-id="a719c-537">![Saving the network configuration as a picture.](images/JJ945604.145a6fb9-58b1-46b1-bbd5-a661ceba07b4(OCS.15).jpg "Saving the network configuration as a picture.")</span></span>

<span data-ttu-id="a719c-538">**Afficher les données de configuration de la topologie réseau CAC :** Les administrateurs Lync Server 2013 peuvent afficher les données de configuration du réseau, telles que les régions réseau, les sites réseau, les profils de bande passante et les adresses IP de sous-réseau de site dans un format textuel à l’aide de l’option Afficher les données de configuration réseau, comme indiqué ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="a719c-538">**View CAC network topology configuration data:** Lync Server 2013 administrators can view related network configuration data such as network regions, network sites, bandwidth profiles, and site subnet IP addresses in a textual format by using the View Network Configuration data option as shown below.</span></span>

<span data-ttu-id="a719c-539">![Affichage des données de configuration réseau.](images/JJ945604.b72a4c21-a042-4d91-bf96-fcb396af0679(OCS.15).jpg "Affichage des données de configuration réseau.")</span><span class="sxs-lookup"><span data-stu-id="a719c-539">![Viewing network configuration data.](images/JJ945604.b72a4c21-a042-4d91-bf96-fcb396af0679(OCS.15).jpg "Viewing network configuration data.")</span></span>

<span data-ttu-id="a719c-540">**Afficher la topologie du réseau CAC sous forme d’arborescence :** Les administrateurs de Lync Server 2013 peuvent afficher les données de configuration du réseau associées dans un style d’affichage de l’arborescence graphique en utilisant le panneau de configuration du côté gauche de la fenêtre outil, comme illustré ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="a719c-540">**View CAC network topology in a tree-view style:** Lync Server 2013 administrators can view related network configuration data in a graphical tree view style by using the control panel on the left side of the tool window as shown below.</span></span>

<span data-ttu-id="a719c-541">![Affichage des données de configuration réseau dans une arborescence.](images/JJ945604.4d924ac9-fd96-430f-b211-ee35b7ef9a23(OCS.15).jpg "Affichage des données de configuration réseau dans une arborescence.")</span><span class="sxs-lookup"><span data-stu-id="a719c-541">![Viewing network configuration data in a tree-view.](images/JJ945604.4d924ac9-fd96-430f-b211-ee35b7ef9a23(OCS.15).jpg "Viewing network configuration data in a tree-view.")</span></span>

<span data-ttu-id="a719c-542">**Définissez des connecteurs personnalisés pour les liens de topologie de réseau CAC (tels que les liens de site à région, région à région et de site à site) :** Les administrateurs Lync Server 2013 peuvent définir des connecteurs graphiques personnalisés pour la configuration du réseau CAC WAN Links à l’aide de l’option paramètres, comme illustré ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="a719c-542">**Define custom connectors for CAC network topology links (such as site-to-region, region-to-region, and site-to-site links):** Lync Server 2013 administrators can define custom graphical connectors for CAC network configuration WAN links by using the Settings option as shown below.</span></span> <span data-ttu-id="a719c-543">Cela permet de différencier les différents types de liaisons réseau configurées dans la configuration réseau.</span><span class="sxs-lookup"><span data-stu-id="a719c-543">This helps differentiate between various types of network links that are provisioned in the network configuration.</span></span>

<span data-ttu-id="a719c-544">![Définir des connecteurs personnalisés pour la topologie du réseau CAC](images/JJ945604.b20bea67-c8e1-453e-b1dd-e2aa17b62566(OCS.15).jpg "Définir des connecteurs personnalisés pour la topologie du réseau CAC")</span><span class="sxs-lookup"><span data-stu-id="a719c-544">![Define custom connectors for CAC network topology](images/JJ945604.b20bea67-c8e1-453e-b1dd-e2aa17b62566(OCS.15).jpg "Define custom connectors for CAC network topology")</span></span>

<span data-ttu-id="a719c-545">**Afficher les informations de site, les informations de région et les stratégies de bande passante de mise en service de la topologie réseau CAC :** Les administrateurs Lync Server 2013 peuvent afficher les informations relatives à la région réseau CAC, les informations de site et les informations de configuration de la bande passante CAC à l’aide des options indiquées ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="a719c-545">**View CAC network topology site information, region information, and provisioned bandwidth policies:** Lync Server 2013 administrators can view related CAC network region information, site information, and CAC bandwidth provisioning information by using options shown below.</span></span> <span data-ttu-id="a719c-546">(Par exemple, cliquez sur **info** dans une région réseau ou un objet de site réseau.)</span><span class="sxs-lookup"><span data-stu-id="a719c-546">(For example, click **Info** in a network region or network site object.)</span></span>

<span data-ttu-id="a719c-547">![Définition de connecteurs personnalisés pour votre réseau.](images/JJ945604.26262c75-4342-41c3-bc98-1793aa6a7713(OCS.15).jpg "Définition de connecteurs personnalisés pour votre réseau.")</span><span class="sxs-lookup"><span data-stu-id="a719c-547">![Defining custom connectors for your network.](images/JJ945604.26262c75-4342-41c3-bc98-1793aa6a7713(OCS.15).jpg "Defining custom connectors for your network.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="a719c-548">Résumé</span><span class="sxs-lookup"><span data-stu-id="a719c-548">Summary</span></span>

<span data-ttu-id="a719c-549">Cet outil peut être une ressource précieuse pour les administrateurs Lync Server 2013 qui voudraient afficher la topologie de réseau CAC pour leur déploiement dans un format graphique.</span><span class="sxs-lookup"><span data-stu-id="a719c-549">This tool can be a valuable resource to Lync Server 2013 administrators who would like to view CAC network topology for their deployment in a graphical format.</span></span>

</div>

</div>

<div>

## <a name="response-group-agent-live"></a><span data-ttu-id="a719c-550">Response Group agent Live</span><span class="sxs-lookup"><span data-stu-id="a719c-550">Response Group Agent Live</span></span>

<span data-ttu-id="a719c-551">L’application Response Group offre aux agents la possibilité d’accéder à des informations en temps réel utiles à l’aide de son service Web intégré.</span><span class="sxs-lookup"><span data-stu-id="a719c-551">The Response Group application gives agents the ability to access useful real-time information using its built-in Web service.</span></span> <span data-ttu-id="a719c-552">Malheureusement, aucune vue graphique de ces données n’est disponible en dehors de l’application.</span><span class="sxs-lookup"><span data-stu-id="a719c-552">Unfortunately, no graphical view of this data is available outside the application.</span></span> <span data-ttu-id="a719c-553">L’outil Response Group agent Live Resource Kit résout ce problème en fournissant un moyen simple et graphique d’accéder à ces informations, améliorés par des informations logicielles de communication en temps réel de Microsoft Lync 2013, telles que la présence d’autres agents.</span><span class="sxs-lookup"><span data-stu-id="a719c-553">The Response Group Agent Live Resource Kit tool solves this issue by providing a simple and graphical way to access this information, enhanced with real-time Microsoft Lync 2013 communications software information such as the presence of other agents.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="a719c-554">Description</span><span class="sxs-lookup"><span data-stu-id="a719c-554">Description</span></span>

<span data-ttu-id="a719c-555">Response Group agent Live est une application Windows qui fournit des fonctionnalités de connexion et de déconnexion, ainsi que des informations en temps réel (telles que l’appartenance à un groupe et le nombre actuel d’appels) aux agents Response Group.</span><span class="sxs-lookup"><span data-stu-id="a719c-555">Response Group Agent Live is a Windows application that provides sign-in and sign-out functionality and some real-time information (such as group membership and current number of calls) to Response Group agents.</span></span> <span data-ttu-id="a719c-556">Il s’agit d’une version améliorée de la page groupes d’agents (accessible à partir de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="a719c-556">It is meant to be an enhanced version of the Agent Groups page (accessible from Lync 2013.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="a719c-557">Objectif</span><span class="sxs-lookup"><span data-stu-id="a719c-557">Purpose</span></span>

<span data-ttu-id="a719c-558">L’application Response Group place en file d’attente les appels entrants, puis les achemine vers les groupes d’agents.</span><span class="sxs-lookup"><span data-stu-id="a719c-558">The Response Group application queues incoming calls, and then routes them to agent groups.</span></span> <span data-ttu-id="a719c-559">Pour prendre des décisions éclairées concernant les appels à traiter, les agents peuvent accéder aux informations en temps réel sur leurs groupes d’agents, telles que les autres agents disponibles et le nombre d’appels en attente dans chaque file d’attente.</span><span class="sxs-lookup"><span data-stu-id="a719c-559">To make informed decisions about which calls to service, agents can access real-time information about their agent groups, such as what other agents are available and how many calls are waiting in each queue.</span></span> <span data-ttu-id="a719c-560">Ces informations, initialement accessibles uniquement par le biais du service Response Group, sont mises à disposition de manière intuitive par Response Group agent Live.</span><span class="sxs-lookup"><span data-stu-id="a719c-560">This information, initially accessible only through the Response Group service, is made available in an intuitive way by Response Group Agent Live.</span></span>

<div>

## <a name="features"></a><span data-ttu-id="a719c-561">Fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="a719c-561">Features</span></span>

<span data-ttu-id="a719c-562">L’outil Response Group agent Live est basé sur le service Response Group et le kit de développement logiciel (SDK) Microsoft Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="a719c-562">The Response Group Agent Live tool is built on the Response Group service and the Microsoft Lync 2013 SDK.</span></span> <span data-ttu-id="a719c-563">Il fournit aux agents Response Group les informations et les fonctionnalités disponibles auprès du service Response Group (par exemple, l’appartenance à un groupe, la présence d’autres agents et le nombre d’appels en attente).</span><span class="sxs-lookup"><span data-stu-id="a719c-563">It provides Response Group agents the information and capabilities that are available from the Response Group service (such as group membership, presence of other agents, and number of waiting calls).</span></span>

<span data-ttu-id="a719c-564">La figure ci-dessous illustre l’interface principale de Response Group agent Live.</span><span class="sxs-lookup"><span data-stu-id="a719c-564">The figure below illustrates the main interface of Response Group Agent Live.</span></span>

<span data-ttu-id="a719c-565">![Outil Response Group agent Live.](images/JJ945604.63cb0374-a6ef-4a59-b60e-bec86a880d09(OCS.15).jpg "Outil Response Group agent Live.")</span><span class="sxs-lookup"><span data-stu-id="a719c-565">![The Response Group Agent Live tool.](images/JJ945604.63cb0374-a6ef-4a59-b60e-bec86a880d09(OCS.15).jpg "The Response Group Agent Live tool.")</span></span>

<span data-ttu-id="a719c-566">Les trois fonctionnalités principales suivantes sont disponibles pour les agents dans Response Group agent Live :</span><span class="sxs-lookup"><span data-stu-id="a719c-566">The following three main features are available for agents in Response Group Agent Live:</span></span>

  - <span data-ttu-id="a719c-567">**Connexion/déconnexion :** Contrairement à la page des groupes d’agents (accessible à partir de Lync 2013), Response Group agent Live autorise uniquement les agents à se connecter ou à déconnecter tous les groupes d’agents en même temps.</span><span class="sxs-lookup"><span data-stu-id="a719c-567">**Sign-in/out:** Contrary to the Agent Groups page (accessible from Lync 2013), Response Group Agent Live allows only agents to sign-in or out of all agent groups at once.</span></span> <span data-ttu-id="a719c-568">Cette application propose trois méthodes rapides pour la connexion et la déconnexion des agents :</span><span class="sxs-lookup"><span data-stu-id="a719c-568">This application provides three quick ways for agents to sign in or out:</span></span>
    
      - <span data-ttu-id="a719c-569">Cliquez sur le bouton se connecter/déconnecter (vert et rouge) dans l’application.</span><span class="sxs-lookup"><span data-stu-id="a719c-569">Click the Sign-in/out (green and red) buttons within the application.</span></span>
    
      - <span data-ttu-id="a719c-570">Cliquez avec le bouton droit sur l’icône de la barre d’état système, puis sélectionnez se connecter ou se déconnecter.</span><span class="sxs-lookup"><span data-stu-id="a719c-570">Right-click the system tray icon, and select sign in or sign out.</span></span>
    
      - <span data-ttu-id="a719c-571">Utilisation de raccourcis clavier configurables.</span><span class="sxs-lookup"><span data-stu-id="a719c-571">Using configurable keyboard shortcuts.</span></span>

  - <span data-ttu-id="a719c-572">**Appartenance au groupe :** Lorsqu’un groupe d’agents est sélectionné, Response Group agent Live affiche la liste des agents de ce groupe dans le volet de droite.</span><span class="sxs-lookup"><span data-stu-id="a719c-572">**Group membership:** When an agent group is selected, Response Group Agent Live displays the list of agents in this group in the right pane.</span></span> <span data-ttu-id="a719c-573">Si Lync 2013 est exécuté sur le même ordinateur que cette application, les informations de présence et la carte de visite s’affichent dans l’agent Response Group agent Live.</span><span class="sxs-lookup"><span data-stu-id="a719c-573">If Lync 2013 is running on the same computer as this application, presence information and the contact card are displayed in the Response Group Agent Live.</span></span> <span data-ttu-id="a719c-574">Les agents peuvent envoyer un message instantané ou appeler d’autres agents directement à partir de là.</span><span class="sxs-lookup"><span data-stu-id="a719c-574">Agents can send an IM or call other agents directly from there.</span></span>

  - <span data-ttu-id="a719c-575">**Statistiques en temps réel :** Response Group agent Live fournit des statistiques en temps réel pour tous les groupes d’agents.</span><span class="sxs-lookup"><span data-stu-id="a719c-575">**Real-time statistics:** Response Group Agent Live provides real-time statistics for all agent groups.</span></span> <span data-ttu-id="a719c-576">La fréquence de mise à jour est d’une minute.</span><span class="sxs-lookup"><span data-stu-id="a719c-576">The update frequency is one minute.</span></span> <span data-ttu-id="a719c-577">Lorsqu’un groupe Response Group répond à un appel, un indicateur visuel est ajouté en regard du nom du groupe avec le nombre actuel d’appels en file d’attente.</span><span class="sxs-lookup"><span data-stu-id="a719c-577">When a call is answered by a Response Group, a visual indicator is added next to the group name with the current number of queued calls.</span></span> <span data-ttu-id="a719c-578">La suspension du pointeur sur un groupe affiche également le temps d’attente le plus long.</span><span class="sxs-lookup"><span data-stu-id="a719c-578">Pausing the pointer over a group also displays the longest waiting time.</span></span>

</div>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="a719c-579">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="a719c-579">Requirements</span></span>

<span data-ttu-id="a719c-580">Response Group agent Live requiert .NET Framework 4,0.</span><span class="sxs-lookup"><span data-stu-id="a719c-580">Response Group Agent Live requires the .NET Framework 4.0.</span></span> <span data-ttu-id="a719c-581">En outre, pour tirer parti des fonctionnalités de présence et de carte de visite, Lync 2013 doit être installé localement (et être en cours d’exécution).</span><span class="sxs-lookup"><span data-stu-id="a719c-581">In addition, to take advantage of the presence and contact card features, Lync 2013 must be installed locally (and be running).</span></span>

<div>

## <a name="configuration"></a><span data-ttu-id="a719c-582">Configuration</span><span class="sxs-lookup"><span data-stu-id="a719c-582">Configuration</span></span>

<span data-ttu-id="a719c-583">Response Group agent Live peut être personnalisé en fonction des préférences individuelles à l’aide de la boîte de dialogue Options de l’application.</span><span class="sxs-lookup"><span data-stu-id="a719c-583">Response Group Agent Live can be customized to individual preferences by using the Options dialog box in the application.</span></span> <span data-ttu-id="a719c-584">En outre, l’administrateur peut définir l’adresse de l’hôte par défaut en modifiant directement la propriété defaultHostAddress du fichier RGAgentLive.exe.config.</span><span class="sxs-lookup"><span data-stu-id="a719c-584">In addition, the administrator can define the default host address by editing directly the defaultHostAddress property of the RGAgentLive.exe.config file.</span></span>

<span data-ttu-id="a719c-585">La figure ci-dessous illustre la boîte de dialogue Options que les agents peuvent utiliser pour configurer l’adresse hôte et les touches de raccourci.</span><span class="sxs-lookup"><span data-stu-id="a719c-585">The figure below illustrates the Options dialog box that agents can use to configure the host address and shortcut keys.</span></span> <span data-ttu-id="a719c-586">Pour accéder à cette boîte de dialogue, cliquez sur le bouton options en haut à droite de l’interface principale.</span><span class="sxs-lookup"><span data-stu-id="a719c-586">This dialog is accessed by clicking the Options button on the top right of the main interface.</span></span>

<span data-ttu-id="a719c-587">![Boîte de dialogue Options de l’agent Response Group.](images/JJ945604.3cc15e29-8699-45ab-90c3-e1565fa6ebf6(OCS.15).jpg "Boîte de dialogue Options de l’agent Response Group.")</span><span class="sxs-lookup"><span data-stu-id="a719c-587">![The Response Group Agent Live Options dialog box.](images/JJ945604.3cc15e29-8699-45ab-90c3-e1565fa6ebf6(OCS.15).jpg "The Response Group Agent Live Options dialog box.")</span></span>

<span data-ttu-id="a719c-588">Les trois paramètres suivants peuvent être personnalisés dans la configuration de Response Group agent Live :</span><span class="sxs-lookup"><span data-stu-id="a719c-588">The following three different settings can be customized in the Response Group Agent Live configuration:</span></span>

  - <span data-ttu-id="a719c-589">Adresse de l’hôte : il s’agit généralement du nom de domaine complet du pool de l’agent.</span><span class="sxs-lookup"><span data-stu-id="a719c-589">Host address: This is typically the web pool FQDN belonging to the agent’s home pool.</span></span> <span data-ttu-id="a719c-590">L’adresse exacte du service Response Group est automatiquement dérivée en arrière-plan à partir de ces informations (en ajoutant le chemin d’accès approprié après l’hôte).</span><span class="sxs-lookup"><span data-stu-id="a719c-590">The exact Response Group service address is automatically derived in the background from this information (by appending the right path after the host).</span></span>

  - <span data-ttu-id="a719c-591">Raccourcis : les raccourcis exacts de connexion/déconnexion peuvent être personnalisés.</span><span class="sxs-lookup"><span data-stu-id="a719c-591">Shortcuts: The exact shortcuts to sign-in/out can be customized.</span></span> <span data-ttu-id="a719c-592">La seule limitation est que les deux raccourcis doivent contenir la clé « Windows logo » (en plus d’au moins une autre clé).</span><span class="sxs-lookup"><span data-stu-id="a719c-592">The only limitation is that both shortcuts must contain the “Windows Logo” key (in addition to at least another key).</span></span>

  - <span data-ttu-id="a719c-593">Démarrez avec Windows : l’application peut être configurée pour démarrer automatiquement avec Windows.</span><span class="sxs-lookup"><span data-stu-id="a719c-593">Start with Windows: The application can be configured to start automatically with Windows.</span></span>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="a719c-594">Exemples</span><span class="sxs-lookup"><span data-stu-id="a719c-594">Examples</span></span>

<span data-ttu-id="a719c-595">La figure ci-dessous illustre comment appeler ou envoyer un message instantané à un autre agent en cliquant avec le bouton droit sur le contact dans le volet de droite.</span><span class="sxs-lookup"><span data-stu-id="a719c-595">The figure below illustrates how to call or send an IM to another agent by right-clicking the contact in the right pane.</span></span>

<span data-ttu-id="a719c-596">![Passer un appel ou envoyer un message instantané.](images/JJ945604.009cebe0-5a93-4745-89c3-8a16c7c13009(OCS.15).jpg "Passer un appel ou envoyer un message instantané.")</span><span class="sxs-lookup"><span data-stu-id="a719c-596">![Making a call or sending an IM.](images/JJ945604.009cebe0-5a93-4745-89c3-8a16c7c13009(OCS.15).jpg "Making a call or sending an IM.")</span></span>

<span data-ttu-id="a719c-597">La figure ci-dessous illustre la manière dont Response Group agent Live affiche le nombre actuel d’appels dans la file d’attente et le délai d’attente le plus long parmi tous les appels entrants.</span><span class="sxs-lookup"><span data-stu-id="a719c-597">The figure below illustrates how Response Group Agent Live displays the current number of calls in the queue and the longest waiting time among all these incoming calls.</span></span>

<span data-ttu-id="a719c-598">![Affichage des informations de file d’attente.](images/JJ945604.131d7f79-b7ed-41f5-a9da-ffc556e31037(OCS.15).jpg "Affichage des informations de file d’attente.")</span><span class="sxs-lookup"><span data-stu-id="a719c-598">![Viewing queue information.](images/JJ945604.131d7f79-b7ed-41f5-a9da-ffc556e31037(OCS.15).jpg "Viewing queue information.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="a719c-599">Résumé</span><span class="sxs-lookup"><span data-stu-id="a719c-599">Summary</span></span>

<span data-ttu-id="a719c-600">La connexion et la déconnexion rapides, l’appartenance à un groupe et les statistiques en temps réel de base sont des fonctionnalités intéressantes de l’agent Response Group qui ne sont disponibles qu’en dehors de l’application à partir du service Response Group.</span><span class="sxs-lookup"><span data-stu-id="a719c-600">Fast sign-in and sign-out, group membership, and basic real-time statistics are interesting Response Group agent features that are only available outside the application from the Response Group service.</span></span> <span data-ttu-id="a719c-601">Avec l’outil Response Group agent Live Resource Kit, les administrateurs Lync peuvent fournir à leurs agents une application Windows qui leur permet d’effectuer des tâches de manière plus rapide et graphique.</span><span class="sxs-lookup"><span data-stu-id="a719c-601">With the Response Group Agent Live Resource Kit tool, Lync administrators can provide their agents with a Windows application that allows them to perform tasks in a faster and graphical way.</span></span>

</div>

</div>

<div>

## <a name="sefautil"></a><span data-ttu-id="a719c-602">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="a719c-602">SEFAUtil</span></span>

<span data-ttu-id="a719c-603">SEFAUtil (Secondary Extension Feature activation) est un outil de ligne de commande qui permet aux administrateurs de logiciels et aux agents du support technique de Microsoft Lync Server 2013 de configurer la sonnerie de délégué, le transfert d’appel, la sonnerie simultanée, les paramètres d’appel d’équipe et la prise d’appel de groupe pour le compte d’un utilisateur Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a719c-603">SEFAUtil (secondary extension feature activation) is a command-line tool that enables Microsoft Lync Server 2013 communications software administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Lync Server 2013 user.</span></span> <span data-ttu-id="a719c-604">L’outil permet également aux administrateurs d’interroger les paramètres de routage des appels publiés pour un utilisateur particulier. L’outil SEFAUtil permet à l’administrateur d’activer/de désactiver/modifier le transfert d’appel ou de sonner simultanément au nom de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a719c-604">The tool also allows administrators to query the call-routing settings that are published for a particular user.The SEFAUtil tool allows the administrator to enable/disable/modify call forwarding or simultaneously ringing on behalf of the user.</span></span> <span data-ttu-id="a719c-605">L’administrateur peut spécifier la cible (sous la forme d’un URI SIP) ou utiliser une cible qui a déjà été publiée par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a719c-605">The administrator can specify the target (in the form of a SIP URI) or use a target that has already been published by the user.</span></span> <span data-ttu-id="a719c-606">Cet outil permet également aux administrateurs d’ajouter ou de supprimer des délégués ou des membres du groupe d’appel d’équipe au nom de l’utilisateur. Cet outil est basé sur Microsoft Unified Communications Managed API (UCMA) 3,0 et exige que les administrateurs créent une application approuvée dans le magasin central de gestion pour SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="a719c-606">This tool also allows administrators to add or remove delegates or team-call group members on behalf of the user.This tool is built on Microsoft Unified Communications Managed API (UCMA) 3.0 and requires that administrators create a trusted application in the Central Management store for SEFAUtil</span></span>

<span data-ttu-id="a719c-607">SEFAUtil (option d’activation de la fonctionnalité d’extension secondaire) permet aux administrateurs et aux agents de support technique Lync Server 2013 de configurer la sonnerie des délégués, le transfert d’appel, la sonnerie simultanée, les paramètres d’appel d’équipe et la prise d’appel de groupe pour le compte d’un utilisateur Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a719c-607">SEFAUtil (secondary extension feature activation) enables Lync Server 2013 administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Lync Server 2013 user.</span></span> <span data-ttu-id="a719c-608">Cet outil permet également aux administrateurs d’interroger les paramètres de routage des appels publiés pour un utilisateur particulier.</span><span class="sxs-lookup"><span data-stu-id="a719c-608">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="a719c-609">Description</span><span class="sxs-lookup"><span data-stu-id="a719c-609">Description</span></span>

<span data-ttu-id="a719c-610">La version actuelle de SEFAUtil n’est qu’un outil de ligne de commande ; Il n’y a pas d’interface utilisateur graphique de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="a719c-610">The current version of SEFAUtil is only a command-line tool; there is no supporting graphical user interface.</span></span> <span data-ttu-id="a719c-611">Cet outil est basé sur Microsoft Unified Communications Managed API (UCMA) 3,0.</span><span class="sxs-lookup"><span data-stu-id="a719c-611">This tool is based on Microsoft Unified Communications Managed API (UCMA) 3.0.</span></span> <span data-ttu-id="a719c-612">Les fonctionnalités de cet outil permettent aux administrateurs et aux agents du support technique d’effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="a719c-612">The features in this tool allow administrators and helpdesk agents to do the following:</span></span>

  - <span data-ttu-id="a719c-613">Afficher tous les paramètres de routage des appels d’un utilisateur (inclut le transfert d’appels, la délégation, la sonnerie simultanée, l’appel d’équipe et la prise d’appel de groupe)</span><span class="sxs-lookup"><span data-stu-id="a719c-613">View all call routing settings for a user (includes call-forwarding, delegation, simultaneous ringing, team-call and group call pickup)</span></span>

  - <span data-ttu-id="a719c-614">Activer/désactiver/modifier le paramètre de transfert d’appel (y compris la destination et le minuteur de non-réponse)</span><span class="sxs-lookup"><span data-stu-id="a719c-614">Enable/disable/modify call-forwarding setting (includes destination and no-answer timer)</span></span>

  - <span data-ttu-id="a719c-615">Activer/désactiver/modifier les configurations immédiates de transfert d’appel</span><span class="sxs-lookup"><span data-stu-id="a719c-615">Enable/disable/modify call-forwarding immediate configurations</span></span>

  - <span data-ttu-id="a719c-616">Activer/désactiver/modifier les paramètres de délégation</span><span class="sxs-lookup"><span data-stu-id="a719c-616">Enable/disable/modify delegation settings</span></span>

  - <span data-ttu-id="a719c-617">Activer/désactiver/modifier les paramètres du groupe d’appel d’équipe</span><span class="sxs-lookup"><span data-stu-id="a719c-617">Enable/disable/modify team-call group settings</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a719c-618">Nouveauté de l’outil SEFAUtil de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a719c-618">New in Lync Server 2013 SEFAUtil tool</span></span>

    
    </div>

  - <span data-ttu-id="a719c-619">Activer/désactiver/modifier les paramètres de sonnerie simultanée (il s’agit de la destination)</span><span class="sxs-lookup"><span data-stu-id="a719c-619">Enable/disable/modify simultaneous ringing settings (includes destination)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a719c-620">Nouveauté de l’outil SEFAUtil de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a719c-620">New in Lync Server 2013 SEFAUtil tool</span></span>

    
    </div>

  - <span data-ttu-id="a719c-621">Activer/désactiver/modifier les paramètres de prise d’appel de groupe</span><span class="sxs-lookup"><span data-stu-id="a719c-621">Enable/disable/modify group call pickup settings</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="a719c-622">Nouveauté de l’outil SEFAUtil de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a719c-622">New in Lync Server 2013 SEFAUtil tool</span></span>

    
    </div>

<span data-ttu-id="a719c-623">Cet outil présente les limitations suivantes :</span><span class="sxs-lookup"><span data-stu-id="a719c-623">This tool has the following limitations:</span></span>

  - <span data-ttu-id="a719c-624">Pris en charge uniquement pour les utilisateurs hébergés dans un pool Lync Server</span><span class="sxs-lookup"><span data-stu-id="a719c-624">Supported only for users homed in a Lync Server pool</span></span>

  - <span data-ttu-id="a719c-625">La modification en bloc des paramètres de routage des appels pour plusieurs utilisateurs n’est pas prise en charge</span><span class="sxs-lookup"><span data-stu-id="a719c-625">Bulk-edit of call routing settings for several users is not supported</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="a719c-626">Output</span><span class="sxs-lookup"><span data-stu-id="a719c-626">Output</span></span>

<span data-ttu-id="a719c-627">La version actuelle de cet outil fournit uniquement des résultats dans la fenêtre d’invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="a719c-627">The current version of this tool provides output only in the Command Prompt window.</span></span> <span data-ttu-id="a719c-628">Pour plus d’informations, consultez la section exemples plus loin dans ce document.</span><span class="sxs-lookup"><span data-stu-id="a719c-628">For details, see the Examples section later in this document.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="a719c-629">Objectif</span><span class="sxs-lookup"><span data-stu-id="a719c-629">Purpose</span></span>

<span data-ttu-id="a719c-630">Voici quelques-uns des principaux scénarios dans lesquels cet outil peut être utilisé :</span><span class="sxs-lookup"><span data-stu-id="a719c-630">Following are some of the key scenarios where this tool may be used:</span></span>

  - <span data-ttu-id="a719c-631">Bob est un cadre qui a été déplacé vers la téléphonie Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a719c-631">Bob is an executive and has been moved to Lync Server telephony.</span></span> <span data-ttu-id="a719c-632">Il dispose d’une délégation sur son système PBX existant.</span><span class="sxs-lookup"><span data-stu-id="a719c-632">He has delegation on his existing PBX system.</span></span> <span data-ttu-id="a719c-633">Dans le cadre de la migration vers Lync, l’administrateur peut configurer le routage de Bob afin de refléter sa configuration de délégation préexistante.</span><span class="sxs-lookup"><span data-stu-id="a719c-633">As part of the move to Lync, the administrator is able to configure Bob’s routing to reflect his pre-existing delegation configuration.</span></span>

  - <span data-ttu-id="a719c-634">Alice se rend compte qu’elle attend un appel important de la part de l’un de ses clients.</span><span class="sxs-lookup"><span data-stu-id="a719c-634">Alice is travelling and realizes that she is expecting an important call from one of her customers.</span></span> <span data-ttu-id="a719c-635">Toutefois, elle se trouve dans un hôtel et n’a pas accès à un ordinateur.</span><span class="sxs-lookup"><span data-stu-id="a719c-635">However, she is in a hotel and has no access to a computer.</span></span> <span data-ttu-id="a719c-636">Elle appelle le support technique et demande à son numéro de téléphone mobile tous les appels effectués sur son numéro de travail.</span><span class="sxs-lookup"><span data-stu-id="a719c-636">She calls the helpdesk and requests that they forward to her mobile number all the calls made to her work number.</span></span> <span data-ttu-id="a719c-637">Le personnel du support technique peut effectuer la configuration en son nom.</span><span class="sxs-lookup"><span data-stu-id="a719c-637">The helpdesk personnel are able to do the configuration on her behalf.</span></span>

  - <span data-ttu-id="a719c-638">Les appels de Jean vers son numéro de travail accédant à sa messagerie vocale mobile chaque fois qu’il travaille ; Toutefois, les choses semblent fonctionner correctement dans la plupart des autres emplacements.</span><span class="sxs-lookup"><span data-stu-id="a719c-638">Joe’s calls to his work number are going to his mobile voicemail whenever he is at work; however, things appear to be working correctly in most other locations.</span></span> <span data-ttu-id="a719c-639">Le technicien du service d’assistance peut consulter la configuration de routage de Joe et se dévoiler que Joe a une sonnerie simultanée configurée sur son téléphone mobile.</span><span class="sxs-lookup"><span data-stu-id="a719c-639">The helpdesk technician is able to view Joe’s routing configuration and discovers that Joe has simultaneous ringing configured to his mobile phone.</span></span> <span data-ttu-id="a719c-640">Le technicien demande à Joe la couverture mobile au niveau de son bureau et est en mesure de déterminer que la règle de sonnerie simultanée est ce qui provoque l’accès des appels à la messagerie vocale mobile de Jean quand sa couverture réseau est médiocre.</span><span class="sxs-lookup"><span data-stu-id="a719c-640">The technician asks Joe about the mobile coverage at his office and is able to determine that the simultaneous ringing rule is what is causing the calls to go to Joe’s mobile voicemail when his network coverage is poor.</span></span>

  - <span data-ttu-id="a719c-641">Mike est un nouvel employé chez contoso et il rejoint une nouvelle équipe sur laquelle tous les membres sont configurés pour l’appel d’équipe, lorsqu’il est activé pour Microsoft Lync, l’administrateur est en mesure de définir ses paramètres de groupe d’appel d’équipe afin d’inclure tous ses nouveaux membres de l’équipe, en outre, l’administrateur ajoute Mike en tant que membre du groupe d’appel d’équipe.</span><span class="sxs-lookup"><span data-stu-id="a719c-641">Mike is a new employee at Contoso and he’s joining a new team on which all members are configured for team-call, when being enabled for Microsoft Lync, the administrator is able to set his team-call group settings to include all his new team members, additionally, the administrator adds Mike as a team-call group member for each of the members in his team.</span></span>

  - <span data-ttu-id="a719c-642">Une pratique de service clientèle dans le département des ressources humaines de contoso est de fournir un service personnel à tous les appelants depuis le premier appel.</span><span class="sxs-lookup"><span data-stu-id="a719c-642">A customer service practice in the human resources department at Contoso is to provide personal service for all callers since the first call.</span></span> <span data-ttu-id="a719c-643">Étant donné que tous les membres du service se sont très proches l’un de l’autre, le fait que tous les téléphones sonnent en même temps avec l’appel d’équipe est très gênant pour l’équipe.</span><span class="sxs-lookup"><span data-stu-id="a719c-643">Given that all members of the department sit very close to each other, having all phones ringing at the same time with team-call is very disruptive for the team.</span></span> <span data-ttu-id="a719c-644">Pour fournir le meilleur service sans interrompre les membres de l’équipe, l’administrateur Lync tire parti de la fonctionnalité de prise d’appel de groupe.</span><span class="sxs-lookup"><span data-stu-id="a719c-644">To provide the best service without disrupting the team members, the Lync administrator takes advantage of the Group Call Pickup capability.</span></span> <span data-ttu-id="a719c-645">L’administrateur ajoute tous les membres du service à un groupe de collecte et communique au service le numéro du groupe de collecte.</span><span class="sxs-lookup"><span data-stu-id="a719c-645">The administrator adds all department members to a pickup group and communicates to the department the pickup group number.</span></span> <span data-ttu-id="a719c-646">Lorsque Samantha est absent de son bureau, Jean remarque son sonnerie et il répond à l’appel de son bureau.</span><span class="sxs-lookup"><span data-stu-id="a719c-646">When Samantha is absent from her desk, Joe notices her phone ringing and he proceeds to answer the call from his desk.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="a719c-647">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="a719c-647">Requirements</span></span>

<span data-ttu-id="a719c-648">L’outil SEFAUtil peut être exécuté uniquement sur un ordinateur qui fait partie d’un pool d’applications approuvées.</span><span class="sxs-lookup"><span data-stu-id="a719c-648">The SEFAUtil tool can be run only on a computer that is a part of a Trusted Application Pool.</span></span> <span data-ttu-id="a719c-649">UCMA 3,0 doit être installé sur cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="a719c-649">UCMA 3.0 must be installed on that computer.</span></span> <span data-ttu-id="a719c-650">Pour exécuter l’outil, une nouvelle application approuvée avec l’ID d’application SEFAUtil doit être créée sur ce pool.</span><span class="sxs-lookup"><span data-stu-id="a719c-650">To run the tool, a new Trusted Application with the SEFAUtil application ID must be created on that pool.</span></span>

<span data-ttu-id="a719c-651">**Création d’une application approuvée pour l’outil SEFAUtil**</span><span class="sxs-lookup"><span data-stu-id="a719c-651">**Creating a new Trusted Application for the SEFAUtil tool**</span></span>

1.  <span data-ttu-id="a719c-652">L’outil SEFAUTil peut être exécuté uniquement sur un ordinateur qui fait partie d’un pool d’applications approuvées.</span><span class="sxs-lookup"><span data-stu-id="a719c-652">The SEFAUTil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="a719c-653">Si nécessaire, l’ajout d’un pool en tant que nouveau pool d’applications approuvées peut être réalisé via Lync Server Management Shell avec l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="a719c-653">If needed, adding a pool as a new trusted application pool can be done via the Lync Server Management Shell with the following cmdlet:</span></span>
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a719c-654">UCMA 3,0 doit être installé sur tout ordinateur qui sera utilisé pour exécuter l’outil SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="a719c-654">UCMA 3.0 must be installed on any computer that will be used to run the SEFAUtil tool.</span></span>

    
    </div>

2.  <span data-ttu-id="a719c-655">Une application approuvée doit être définie dans la topologie pour l’outil SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="a719c-655">A trusted application needs to be defined in the topology for the SEFAUtil tool.</span></span> <span data-ttu-id="a719c-656">Pour définir SEFAUtil en tant que nouvelle application approuvée, utilisez Lync Server Management Shell et exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="a719c-656">To define SEFAUtil as a new trusted application, use the Lync Server Management Shell and execute the following cmdlet:</span></span>
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a719c-657">Un autre port peut être utilisé si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="a719c-657">A different port can be used if needed.</span></span>

    
    </div>

3.  <span data-ttu-id="a719c-658">Les modifications de la topologie doivent être activées.</span><span class="sxs-lookup"><span data-stu-id="a719c-658">The topology changes need to be enabled.</span></span> <span data-ttu-id="a719c-659">L’activation des modifications de la topologie peut être réalisée via Lync Server Management Shell en exécutant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="a719c-659">Enabling the topology changes can be done via the Lync Server Management Shell by executing the following cmdlet:</span></span>
    
        Enable-CsToplogy

4.  <span data-ttu-id="a719c-660">Si nécessaire, installez les outils du kit de ressources Lync Server 2013 dans le serveur qui sera utilisé pour exécuter l’outil SEFAUtil (le serveur doit faire partie d’un pool d’applications approuvées).</span><span class="sxs-lookup"><span data-stu-id="a719c-660">If needed, install the Lync Server 2013 Resource Kit Tools in the server that will be used to run the SEFAUtil tool (the server must be part of a trusted application pool).</span></span>

5.  <span data-ttu-id="a719c-661">Vérifiez que le SEFAUtil s’exécute correctement.</span><span class="sxs-lookup"><span data-stu-id="a719c-661">Verify the SEFAUtil is running correctly.</span></span> <span data-ttu-id="a719c-662">Pour ce faire, exécutez l’outil à partir d’une invite de commande Windows avec des privilèges d’administrateur pour afficher les paramètres de transfert d’appel d’un utilisateur dans le déploiement.</span><span class="sxs-lookup"><span data-stu-id="a719c-662">To do this, run the tool from a windows command prompt with administrator privileges to display the call forwarding settings of a user in the deployment.</span></span> <span data-ttu-id="a719c-663">Par défaut, l’outil se trouve dans : "... \\ Fichiers programme \\ Microsoft Lync Server 2013 \\ reskit».</span><span class="sxs-lookup"><span data-stu-id="a719c-663">By default the tool will be located in: “…\\Program Files\\Microsoft Lync Server 2013\\Reskit”.</span></span> <span data-ttu-id="a719c-664">Pour afficher les paramètres de transfert d’appel d’un utilisateur, utilisez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="a719c-664">To display the call forwarding settings of a user, use the following command:</span></span>
    
        SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
    
    <span data-ttu-id="a719c-665">Les paramètres de transfert d’appel de l’utilisateur doivent être affichés.</span><span class="sxs-lookup"><span data-stu-id="a719c-665">The call forwarding settings of the user should be displayed.</span></span>

<div>

## <a name="group-call-pickup"></a><span data-ttu-id="a719c-666">Prise d’appel de groupe</span><span class="sxs-lookup"><span data-stu-id="a719c-666">Group Call Pickup</span></span>

<span data-ttu-id="a719c-667">La prise d’appel de groupe nécessite une configuration supplémentaire dans Lync Server pour que la capacité soit entièrement activée.</span><span class="sxs-lookup"><span data-stu-id="a719c-667">Group Call Pickup requires additional configuration in Lync Server for the capability to be fully enabled.</span></span> <span data-ttu-id="a719c-668">Avant d’affecter des groupes de collecte aux utilisateurs, reportez-vous à la documentation du produit de prise d’appel de groupe pour les étapes de planification et de déploiement de cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="a719c-668">Before assigning pickup groups to users, refer to the Group Call Pickup product documentation for the planning and deployment steps of this capability.</span></span>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="a719c-669">Exemples</span><span class="sxs-lookup"><span data-stu-id="a719c-669">Examples</span></span>

<div>

## <a name="display-current-call-handling-settings"></a><span data-ttu-id="a719c-670">Afficher les paramètres de gestion des appels actifs</span><span class="sxs-lookup"><span data-stu-id="a719c-670">Display Current Call Handling Settings</span></span>

<span data-ttu-id="a719c-671">La commande suivante affiche le traitement des appels pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a719c-671">The following command displays the call handling for the user.</span></span> `SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com`

<div>


> [!NOTE]  
> <span data-ttu-id="a719c-672">Cet exemple utilise le commutateur <STRONG>/Server</STRONG> pour spécifier le serveur Lync auquel se connecter.</span><span class="sxs-lookup"><span data-stu-id="a719c-672">This example uses the <STRONG>/server</STRONG> switch to specify the Lync Server to connect to.</span></span>



</div>

<span data-ttu-id="a719c-673">**Résultat**</span><span class="sxs-lookup"><span data-stu-id="a719c-673">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:20
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-call-forwardno-answer-destination"></a><span data-ttu-id="a719c-674">Définir la destination de transfert d’appel/pas de réponse</span><span class="sxs-lookup"><span data-stu-id="a719c-674">Set the Call Forward/No Answer Destination</span></span>

<span data-ttu-id="a719c-675">Cet exemple montre comment définir la destination de transfert d’appel/de réponse et le retard de l’anneau.</span><span class="sxs-lookup"><span data-stu-id="a719c-675">This example sets the call forward/no answer destination and the ring delay.</span></span> <span data-ttu-id="a719c-676">Ici, le commutateur/Server n’est pas fourni ; SEFAUtil tente de découvrir automatiquement le serveur Lync.</span><span class="sxs-lookup"><span data-stu-id="a719c-676">Here, the /server switch is not provided; SEFAUtil attempts to autodiscover the Lync Server.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone

<span data-ttu-id="a719c-677">**Résultat**</span><span class="sxs-lookup"><span data-stu-id="a719c-677">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="enable-call-forwarding-immediately"></a><span data-ttu-id="a719c-678">Activer le transfert d’appel immédiatement</span><span class="sxs-lookup"><span data-stu-id="a719c-678">Enable Call Forwarding Immediately</span></span>

<span data-ttu-id="a719c-679">Cet exemple active immédiatement le transfert d’appel à un autre utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a719c-679">This example immediately enables call-forwarding to another user.</span></span>

    SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com

<span data-ttu-id="a719c-680">**Résultat**</span><span class="sxs-lookup"><span data-stu-id="a719c-680">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Forward immediate to: sip:anders@contoso.com

</div>

<div>

## <a name="disable-call-forwarding-immediately"></a><span data-ttu-id="a719c-681">Désactiver immédiatement le transfert d’appel</span><span class="sxs-lookup"><span data-stu-id="a719c-681">Disable Call Forwarding Immediately</span></span>

<span data-ttu-id="a719c-682">Cet exemple désactive immédiatement le transfert d’appel.</span><span class="sxs-lookup"><span data-stu-id="a719c-682">This example immediately disables call forwarding.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com  /disablefwdimmediate

<span data-ttu-id="a719c-683">**Résultat**</span><span class="sxs-lookup"><span data-stu-id="a719c-683">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a><span data-ttu-id="a719c-684">Ajouter un utilisateur en tant que délégué et configurer la sonnerie simultanée des délégués</span><span class="sxs-lookup"><span data-stu-id="a719c-684">Add a User as a Delegate and Set Up Simultaneous Ringing of Delegates</span></span>

<span data-ttu-id="a719c-685">Cet exemple ajoute un utilisateur en tant que délégué et configure la sonnerie simultanée des délégués.</span><span class="sxs-lookup"><span data-stu-id="a719c-685">This example adds a user as a delegate and sets up simultaneous ringing of delegates.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates

<span data-ttu-id="a719c-686">**Résultat**</span><span class="sxs-lookup"><span data-stu-id="a719c-686">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simultaneously Ringing Delegates: sip:joe@contoso.com

</div>

<div>

## <a name="change-simultaneous-ringing-rule-of-delegates"></a><span data-ttu-id="a719c-687">Modifier la règle de sonnerie simultanée des délégués</span><span class="sxs-lookup"><span data-stu-id="a719c-687">Change Simultaneous Ringing Rule of Delegates</span></span>

<span data-ttu-id="a719c-688">Cet exemple montre comment remplacer la règle de sonnerie simultanée définie dans l’exemple précédent par la règle de sonnerie différée.</span><span class="sxs-lookup"><span data-stu-id="a719c-688">This example changes the simultaneous ringing rule that was set in the previous example to the delayed ringing rule.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10

<span data-ttu-id="a719c-689">**Résultat**</span><span class="sxs-lookup"><span data-stu-id="a719c-689">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com

</div>

<div>

## <a name="remove-the-delegate"></a><span data-ttu-id="a719c-690">Supprimer le délégué</span><span class="sxs-lookup"><span data-stu-id="a719c-690">Remove the Delegate</span></span>

<span data-ttu-id="a719c-691">Cet exemple supprime le délégué.</span><span class="sxs-lookup"><span data-stu-id="a719c-691">This example removes the delegate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a719c-692">Lorsque le dernier délégué est supprimé, la sonnerie de délégué est automatiquement désactivée.</span><span class="sxs-lookup"><span data-stu-id="a719c-692">When the last delegate is removed, delegate ringing is automatically disabled.</span></span>



</div>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com

<span data-ttu-id="a719c-693">**Résultat**</span><span class="sxs-lookup"><span data-stu-id="a719c-693">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a><span data-ttu-id="a719c-694">Ajouter un délégué et configurer la règle Call-Forward sur les délégués</span><span class="sxs-lookup"><span data-stu-id="a719c-694">Add a Delegate and Set Up the Call-Forward to Delegates Rule</span></span>

<span data-ttu-id="a719c-695">Cet exemple ajoute un délégué et configure la règle appeler-forward to delegates.</span><span class="sxs-lookup"><span data-stu-id="a719c-695">This example adds a delegate and sets up the call-forward to delegates rule.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates

<span data-ttu-id="a719c-696">**Résultat**</span><span class="sxs-lookup"><span data-stu-id="a719c-696">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Forwarding calls to Delegates: sip:anders@contoso.com

</div>

<div>

## <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a><span data-ttu-id="a719c-697">Activer la sonnerie simultanée et définir un numéro de destination</span><span class="sxs-lookup"><span data-stu-id="a719c-697">Enable Simultaneous Ringing and Set a Destination Number</span></span>

<span data-ttu-id="a719c-698">Cet exemple montre comment activer la sonnerie simultanée et définir un numéro de destination de sonnerie simultanée.</span><span class="sxs-lookup"><span data-stu-id="a719c-698">This example enables simultaneous ringing and sets a simultaneous ringing destination number.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring

<div>


> [!NOTE]  
> <span data-ttu-id="a719c-699">Pour modifier le numéro de destination de la sonnerie simultanée d’un utilisateur pour lequel la sonnerie simultanée est déjà activée, conservez la commande avec le commutateur/enablesimulring, sinon le numéro de destination ne sera pas modifié.</span><span class="sxs-lookup"><span data-stu-id="a719c-699">To change the simultaneous ringing destination number of a user that has already simultaneous ringing enabled, keep the command with the /enablesimulring switch, otherwise the destination number will not be changed.</span></span>



</div>

<span data-ttu-id="a719c-700">**Résultat**</span><span class="sxs-lookup"><span data-stu-id="a719c-700">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: True
    Simul_Ringing to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="disable-simultaneous-ringing"></a><span data-ttu-id="a719c-701">Désactiver la sonnerie simultanée</span><span class="sxs-lookup"><span data-stu-id="a719c-701">Disable Simultaneous Ringing</span></span>

<span data-ttu-id="a719c-702">Cet exemple montre comment désactiver la sonnerie simultanée.</span><span class="sxs-lookup"><span data-stu-id="a719c-702">This example disables simultaneous ringing.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablesimulring

<span data-ttu-id="a719c-703">**Résultat**</span><span class="sxs-lookup"><span data-stu-id="a719c-703">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a><span data-ttu-id="a719c-704">Ajouter un membre d’équipe pour Team-Call et configurer la sonnerie simultanée sur le groupe membres de l' Team-Call</span><span class="sxs-lookup"><span data-stu-id="a719c-704">Add a Team Member for Team-Call and Set up Simultaneous Ringing to the Team-Call Members Group</span></span>

<span data-ttu-id="a719c-705">Cet exemple ajoute un membre d’équipe au groupe d’appel d’équipe d’un utilisateur et active la sonnerie simultanée pour le groupe d’appel d’équipe.</span><span class="sxs-lookup"><span data-stu-id="a719c-705">This example adds a team member to the team-call group of a user and enables simultaneous ringing to the team-call group.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam

<div>


> [!NOTE]  
> <span data-ttu-id="a719c-706">L’ajout d’un membre au groupe d’appel d’équipe d’un utilisateur bascule automatiquement la simultanée de sonnerie simultanée des utilisateurs vers sonnerie simultanée son groupe d’appel d’équipe.</span><span class="sxs-lookup"><span data-stu-id="a719c-706">Adding a member to the team-call group of a user will automatically switch the simultaneous ringing settigs of the users to simulring his team-call group.</span></span>



</div>

<span data-ttu-id="a719c-707">**Résultat**</span><span class="sxs-lookup"><span data-stu-id="a719c-707">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Team ringing enabled. Team: sip:anders@contoso.com

</div>

<div>

## <a name="remove-a-member-from-the-team-call-group"></a><span data-ttu-id="a719c-708">Supprimer un membre du groupe Team-Call</span><span class="sxs-lookup"><span data-stu-id="a719c-708">Remove a Member from the Team-Call Group</span></span>

<span data-ttu-id="a719c-709">Cet exemple supprime un membre d’équipe du groupe d’appel d’équipe d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a719c-709">This example removes a team member of the team-call group of a user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com

<div>


> [!NOTE]  
> <span data-ttu-id="a719c-710">Si le membre supprimé est le seul membre du groupe d’appel d’équipe, la sonnerie simultanée du groupe d’appel d’équipe est automatiquement désactivée.</span><span class="sxs-lookup"><span data-stu-id="a719c-710">If the member being removed is the only member of the team-call group, simultaneously ringing to the team-call group will be automatically disabled.</span></span>



</div>

<span data-ttu-id="a719c-711">**Résultat**</span><span class="sxs-lookup"><span data-stu-id="a719c-711">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-delayed-ring-to-the-team-call-group"></a><span data-ttu-id="a719c-712">Définir la sonnerie différée sur le groupe Team-Call</span><span class="sxs-lookup"><span data-stu-id="a719c-712">Set the Delayed Ring to the Team-Call Group</span></span>

<span data-ttu-id="a719c-713">Cet exemple montre comment modifier la sonnerie différée en définissant le paramètre de l’heure du groupe d’appels d’équipe.</span><span class="sxs-lookup"><span data-stu-id="a719c-713">This example changes the delayed ring to the team-call group time setting.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringteam:5

<span data-ttu-id="a719c-714">**Résultat**</span><span class="sxs-lookup"><span data-stu-id="a719c-714">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com

</div>

<div>

## <a name="enable-team-call"></a><span data-ttu-id="a719c-715">Activer Team-Call</span><span class="sxs-lookup"><span data-stu-id="a719c-715">Enable Team-Call</span></span>

<span data-ttu-id="a719c-716">Cet exemple montre comment activer un appel d’équipe pour un utilisateur donné.</span><span class="sxs-lookup"><span data-stu-id="a719c-716">This example enables team-call for a given user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /simulringteam

<div>


> [!NOTE]  
> <span data-ttu-id="a719c-717">Si le groupe d’appel d’équipe de l’utilisateur ne possède pas de membres, Team-Call n’est pas activé.</span><span class="sxs-lookup"><span data-stu-id="a719c-717">If the team-call group of the user has no members, team-call won’t be enabled.</span></span>



</div>

<span data-ttu-id="a719c-718">**Résultat**</span><span class="sxs-lookup"><span data-stu-id="a719c-718">**Output**</span></span>

</div>

<div>

## <a name="disable-team-call"></a><span data-ttu-id="a719c-719">Désactiver Team-Call</span><span class="sxs-lookup"><span data-stu-id="a719c-719">Disable Team-Call</span></span>

<span data-ttu-id="a719c-720">Cet exemple désactive l’appel d’équipe pour un utilisateur donné.</span><span class="sxs-lookup"><span data-stu-id="a719c-720">This example disables team-call for a given user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disableteamcall

<span data-ttu-id="a719c-721">**Résultat**</span><span class="sxs-lookup"><span data-stu-id="a719c-721">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a><span data-ttu-id="a719c-722">Activer la prise d’appel de groupe et attribuer un groupe de prise d’appel à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="a719c-722">Enable Group Call Pickup and Assign a Pickup Group to a User</span></span>

<span data-ttu-id="a719c-723">Cet exemple attribue un groupe de prise d’appel à un utilisateur et active la prise d’appel de groupe.</span><span class="sxs-lookup"><span data-stu-id="a719c-723">This example assigns a pickup group to a user and enables Group Call Pickup.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199

<span data-ttu-id="a719c-724">**Résultat**</span><span class="sxs-lookup"><span data-stu-id="a719c-724">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone

</div>

<div>

## <a name="disable-group-call-pickup"></a><span data-ttu-id="a719c-725">Désactiver la prise d’appel de groupe</span><span class="sxs-lookup"><span data-stu-id="a719c-725">Disable Group Call Pickup</span></span>

<span data-ttu-id="a719c-726">Cet exemple désactive la prise d’appel de groupe pour un utilisateur donné.</span><span class="sxs-lookup"><span data-stu-id="a719c-726">This example disables Group Call Pickup for a given user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablegrouppickup

<div>


> [!NOTE]  
> <span data-ttu-id="a719c-727">Lorsque vous désactivez la prise d’appel de groupe pour un utilisateur, le numéro de groupe qui a été attribué à l’utilisateur n’est pas conservé.</span><span class="sxs-lookup"><span data-stu-id="a719c-727">When you disable Group Call Pickup for a user, the group number that was assigned to the user is not retained.</span></span> <span data-ttu-id="a719c-728">Si vous souhaitez ensuite réactiver la prise d’appel de groupe pour cet utilisateur, vous devez réaffecter le numéro de groupe avec le commutateur/enablegrouppickup.</span><span class="sxs-lookup"><span data-stu-id="a719c-728">If you subsequently want to re-enable Group Call Pickup for that user, you must assign the group number again with the /enablegrouppickup switch.</span></span>



</div>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True

</div>

</div>

</div>

<div>

## <a name="sysprepps1"></a><span data-ttu-id="a719c-729">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="a719c-729">SYSPrep.ps1</span></span>

<div>

## <a name="description"></a><span data-ttu-id="a719c-730">Description</span><span class="sxs-lookup"><span data-stu-id="a719c-730">Description</span></span>

<span data-ttu-id="a719c-731">SYSPrep.ps1 est un script Windows PowerShell qui installe les éléments prérequis de Lync Server 2013 suivants sur votre système d’exploitation Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="a719c-731">SYSPrep.ps1 is a Windows PowerShell script that will install the following Lync Server 2013 prerequisites on your Windows Server 2008 operating system machine.</span></span>

  - <span data-ttu-id="a719c-732">Microsoft .NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="a719c-732">Microsoft .Net Framework 4.5</span></span>

  - <span data-ttu-id="a719c-733">Microsoft SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="a719c-733">Microsoft SQL Server Express</span></span>

  - <span data-ttu-id="a719c-734">Windows PowerShell version 3,0</span><span class="sxs-lookup"><span data-stu-id="a719c-734">Windows Powershell version 3.0</span></span>

  - <span data-ttu-id="a719c-735">Visual C++ 2010 Redistributable</span><span class="sxs-lookup"><span data-stu-id="a719c-735">Visual C++ 2010 Redistributable</span></span>

  - <span data-ttu-id="a719c-736">Mises à jour de Internet Information Server</span><span class="sxs-lookup"><span data-stu-id="a719c-736">Internet Information Server Updates</span></span>

  - <span data-ttu-id="a719c-737">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="a719c-737">Windows Identity Foundation</span></span>

  - <span data-ttu-id="a719c-738">Fichiers principaux Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a719c-738">Lync Server 2013 Core files</span></span>

<span data-ttu-id="a719c-739">Bien que le nom du script soit semblable à l’outil de préparation du système pour les systèmes d’exploitation Microsoft Windows, ils sont différents.</span><span class="sxs-lookup"><span data-stu-id="a719c-739">While the script name is similar to the System Preparation Tool for the Microsoft Windows operating systems, they are different.</span></span> <span data-ttu-id="a719c-740">Ce script installe uniquement les composants requis pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a719c-740">This script will only install the required prerequisites for Lync Server 2013.</span></span> <span data-ttu-id="a719c-741">Une fois ces éléments prérequis installés, l’outil SYSPrep Windows peut ensuite être utilisé pour créer une image du serveur.</span><span class="sxs-lookup"><span data-stu-id="a719c-741">Once those prerequisites are installed, the Windows SYSPrep tool can then be used to create an image of the server.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="a719c-742">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="a719c-742">Requirements</span></span>

<span data-ttu-id="a719c-743">Avant d’exécuter le script SYSPrep.ps1, vous devez copier les fichiers prérequis dans un dossier local sur l’ordinateur du système d’exploitation Windows Server 2008 (par exemple **, D : \\ Setup)**.</span><span class="sxs-lookup"><span data-stu-id="a719c-743">Prior to running the SYSPrep.ps1 script, you must copy the prerequisite files to a local folder on the Windows Server 2008 operating system machine (for example **D:\\Setup)**.</span></span> <span data-ttu-id="a719c-744">Ce dossier doit également inclure une copie des fichiers Lync Server 2013, en particulier **Setup.exe.**</span><span class="sxs-lookup"><span data-stu-id="a719c-744">This folder must also include a copy of the Lync Server 2013 files, specifically **Setup.exe.**</span></span> <span data-ttu-id="a719c-745">Les fichiers prérequis peuvent être téléchargés à partir des emplacements suivants :</span><span class="sxs-lookup"><span data-stu-id="a719c-745">The prerequisite files can be downloaded from the following locations:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a719c-746">Prérequis</span><span class="sxs-lookup"><span data-stu-id="a719c-746">Prerequisite</span></span></th>
<th><span data-ttu-id="a719c-747">Emplacement</span><span class="sxs-lookup"><span data-stu-id="a719c-747">Location</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a719c-748">Microsoft .NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="a719c-748">Microsoft .Net Framework 4.5</span></span></p></td>
<td><p>https://go.microsoft.com/?linkid=9816306</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a719c-749">Microsoft SQL Server Express 2008 R2</span><span class="sxs-lookup"><span data-stu-id="a719c-749">Microsoft SQL Server Express 2008 R2</span></span></p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=23650</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a719c-750">Windows PowerShell version 3,0</span><span class="sxs-lookup"><span data-stu-id="a719c-750">Windows Powershell version 3.0</span></span></p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=34595</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a719c-751">Visual C++ 2010 Redistributable</span><span class="sxs-lookup"><span data-stu-id="a719c-751">Visual C++ 2010 Redistributable</span></span></p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=5555</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a719c-752">Mises à jour de Internet Information Server</span><span class="sxs-lookup"><span data-stu-id="a719c-752">Internet Information Server Updates</span></span></p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=34869</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a719c-753">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="a719c-753">Windows Identity Foundation</span></span></p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=17331</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a719c-754">Lync Server 2013 Setup.exe</span><span class="sxs-lookup"><span data-stu-id="a719c-754">Lync Server 2013 Setup.exe</span></span></p></td>
<td><p><span data-ttu-id="a719c-755">Copier à partir du support Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a719c-755">Copy from Lync Server 2013 media</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="parameter"></a><span data-ttu-id="a719c-756">Paramètre</span><span class="sxs-lookup"><span data-stu-id="a719c-756">Parameter</span></span>

<span data-ttu-id="a719c-757">Le paramètre **– SetupFolder** prend comme argument l’emplacement du répertoire des fichiers prérequis</span><span class="sxs-lookup"><span data-stu-id="a719c-757">The **–SetupFolder** parameter takes as an argument the directory location of the prerequisite files</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="a719c-758">Exemples</span><span class="sxs-lookup"><span data-stu-id="a719c-758">Examples</span></span>

<span data-ttu-id="a719c-759">Pour exécuter le script SYSPrep.ps1 et installer les éléments prérequis de Lync Server 2013, exécutez la commande suivante à partir d’une invite de commandes avec élévation de privilèges :</span><span class="sxs-lookup"><span data-stu-id="a719c-759">To run the SYSPrep.ps1 script and install the Lync Server 2013 prerequisites, run the following command from an elevated command prompt:</span></span>

    ./SysPrep.PS1 -SetupFolder D:\Setup

</div>

</div>

<div>

## <a name="unassigned-number-announcements-migration"></a><span data-ttu-id="a719c-760">Migration des annonces de numéros non attribués</span><span class="sxs-lookup"><span data-stu-id="a719c-760">Unassigned Number Announcements Migration</span></span>

<span data-ttu-id="a719c-761">L’outil de migration des annonces de numéros non attribués permet à un administrateur Lync de déplacer la configuration des numéros non attribués qui est desservi par l’application d’annonce à partir d’un serveur ou d’un pool Lync source vers un pool ou serveur Lync de destination.</span><span class="sxs-lookup"><span data-stu-id="a719c-761">The Unassigned Number Announcements Migration tool enables a Lync administrator to move the unassigned numbers configuration that is serviced by the announcement application from a source Lync Server or Pool to a destination Lync Server or Pool.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="a719c-762">Description</span><span class="sxs-lookup"><span data-stu-id="a719c-762">Description</span></span>

<span data-ttu-id="a719c-763">L’outil de migration des annonces de numéros non attribués est un script Windows PowerShell qui déplace la configuration des numéros non attribués Serviced par l’application d’annonce d’un serveur source ou d’un pool vers un autre serveur ou pool.</span><span class="sxs-lookup"><span data-stu-id="a719c-763">The Unassigned Number Announcements Migration tool is a Windows PowerShell script that moves the unassigned numbers configuration serviced by the announcement application of a source server or pool to a different server or pool.</span></span>

<span data-ttu-id="a719c-764">Lorsqu’il est exécuté, le script de migration des annonces de numéros non attribués effectue les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="a719c-764">When executed, the Unassigned Number Announcements Migration script will perform the following operations:</span></span>

1.  <span data-ttu-id="a719c-765">Déplacez tous les fichiers audio utilisés par les annonces de numéros non attribués de l’application d’annonce hébergée dans le serveur ou le pool source vers le magasin de fichiers du serveur ou du pool de destination.</span><span class="sxs-lookup"><span data-stu-id="a719c-765">Move all the audio files used by the unassigned number announcements of the announcement application hosted in the source server or pool to the file store of the destination server or pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a719c-766">les fichiers audio sont supprimés du pool source une fois qu’ils sont copiés dans le pool de destination.</span><span class="sxs-lookup"><span data-stu-id="a719c-766">the audio files are removed from the source pool once they’re copied to the destination pool.</span></span>

    
    </div>

2.  <span data-ttu-id="a719c-767">Déplacez toutes les annonces de numéros non attribués configurées pour l’application d’annonce hébergée dans le serveur ou le pool source vers le serveur ou le pool de destination.</span><span class="sxs-lookup"><span data-stu-id="a719c-767">Move all unassigned number announcements configured for the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

3.  <span data-ttu-id="a719c-768">Réaffectez toutes les plages de numéros non attribués qui sont desservies par l’application d’annonce hébergée dans le serveur ou le pool source au serveur ou au pool de destination.</span><span class="sxs-lookup"><span data-stu-id="a719c-768">Reassign all the unassigned number ranges that are serviced by the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

<span data-ttu-id="a719c-769">Une fois le script exécuté correctement, toutes les plages de numéros non attribués qui ont été gérées par l’application d’annonce hébergée dans le serveur ou le pool source seront désormais gérées avec la même configuration par le serveur ou le pool de destination.</span><span class="sxs-lookup"><span data-stu-id="a719c-769">After successfully running the script, all the unassigned number ranges that were serviced by the announcement application hosted in the source server or pool will now be serviced with the same configuration by the destination server or pool.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="a719c-770">Output</span><span class="sxs-lookup"><span data-stu-id="a719c-770">Output</span></span>

<span data-ttu-id="a719c-771">Le script **Move-CsAnnouncementConfiguration** indique dans la fenêtre Lync Management Shell où il est exécuté la réussite ou l’échec de l’opération de migration.</span><span class="sxs-lookup"><span data-stu-id="a719c-771">The **Move-CsAnnouncementConfiguration** script indicates in the Lync Management Shell window from where it’s executed the success or failure of the migration operation.</span></span>

<span data-ttu-id="a719c-772">Si l’exécution de l’opération est interrompue par une erreur, les plages de numéros non attribués qui ont été déplacées vers la destination resteront dans une forme opérationnelle et le reste des plages de numéros non attribués à migrer restera dans la source également sous une forme opérationnelle.</span><span class="sxs-lookup"><span data-stu-id="a719c-772">If the execution of the operation is interrupted by any error, the unassigned number ranges that were successfully moved to the destination will remain in the destination in an operational form and the rest of the unassigned number ranges to be migrated will remain in the source as well in an operational form.</span></span> <span data-ttu-id="a719c-773">Pour effectuer une migration complète du reste de la configuration, réexécutez le script après avoir remédié à l’erreur.</span><span class="sxs-lookup"><span data-stu-id="a719c-773">To fully migrate the rest of the configuration, rerun the script after addressing the error.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="a719c-774">Objectif</span><span class="sxs-lookup"><span data-stu-id="a719c-774">Purpose</span></span>

<span data-ttu-id="a719c-775">Le script de migration des annonces de numéros non attribués peut être utilisé dans les trois scénarios suivants :</span><span class="sxs-lookup"><span data-stu-id="a719c-775">The Unassigned Number Announcements Migration script can be used in the following three scenarios:</span></span>

  - <span data-ttu-id="a719c-776">**Migration des paramètres de configuration vers une nouvelle version de Lync Server :** Contoso est en train de migrer vers Lync Server 2013 et, dans le cadre du processus de migration, l’administrateur Lync Server souhaite déplacer la configuration des numéros non attribués Serviced par l’application d’annonce depuis le déploiement de Lync Server 2010 vers le nouveau déploiement Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a719c-776">**Migrating configuration settings to a new version of Lync Server:** Contoso is in the process of migrating to Lync Server 2013 and as part of the migration process the Lync Server administrator would like to move the unassigned numbers configuration serviced by the announcement application from the Lync Server 2010 deployment to the new Lync Server 2013 deployment.</span></span> <span data-ttu-id="a719c-777">Pour déplacer les paramètres de configuration, l’administrateur de Lync Server utilise l’outil de migration annonces de numéros non attribués.</span><span class="sxs-lookup"><span data-stu-id="a719c-777">To move the configuration settings, the Lync Server administrator uses the Unassigned Number Announcements Migration tool.</span></span>

  - <span data-ttu-id="a719c-778">**Restauration d’un déploiement de Lync server 2013 vers Lync server 2010 :** En raison de facteurs inattendus, contoso doit restaurer la migration vers le nouveau déploiement Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a719c-778">**Rolling back a deployment from Lync Server 2013 to Lync Server 2010:** Due unexpected factors, Contoso has to roll back the migration to the new Lync Server 2013 deployment.</span></span> <span data-ttu-id="a719c-779">Pour minimiser les interruptions du service, l’administrateur Lync Server utilise l’outil de migration des annonces de numéros non attribués pour restaurer la configuration du déploiement Lync Server 2013 vers le déploiement Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a719c-779">To minimize disruptions to the service, the Lync Server administrator uses the Unassigned Number Announcements Migration tool to roll back the configuration from the Lync Server 2013 deployment to the Lync Server 2010 deployment.</span></span>

  - <span data-ttu-id="a719c-780">**Transfert de données entre les déploiements Lync :** Contoso est en train de remplacer tous les serveurs d’un pool par des serveurs plus récents.</span><span class="sxs-lookup"><span data-stu-id="a719c-780">**Moving data between Lync deployments:** Contoso is in the process of replacing all the servers of one pool with newer servers.</span></span> <span data-ttu-id="a719c-781">Leur stratégie est le déploiement d’un nouveau pool Lync Server 2013, le déplacement de toutes les données de l’ancien vers le nouveau, puis la désactivation de l’ancien pool.</span><span class="sxs-lookup"><span data-stu-id="a719c-781">Their strategy is to deploy a new Lync Server 2013 pool, move all the data from the old to the new pool, and then deprecate the old pool.</span></span> <span data-ttu-id="a719c-782">Une fois le nouveau pool déployé, l’outil de migration annonces de numéros non attribués est utilisé pour déplacer la configuration de l’ancien pool vers le nouveau.</span><span class="sxs-lookup"><span data-stu-id="a719c-782">Once the new pool is deployed, the Unassigned Number Announcements Migration tool is used to move the configuration from the old pool to the new one.</span></span>

<div>

## <a name="requirements"></a><span data-ttu-id="a719c-783">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="a719c-783">Requirements</span></span>

<span data-ttu-id="a719c-784">Les conditions principales requises pour exécuter correctement l’outil sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="a719c-784">The following are the main requirements needed to successfully run the tool:</span></span>

1.  <span data-ttu-id="a719c-785">Le script doit être exécuté à partir d’un ordinateur sur lequel Lync Server 2013 Management Shell est installé.</span><span class="sxs-lookup"><span data-stu-id="a719c-785">The script must be run from a computer that has Lync Server 2013 Management Shell installed.</span></span>

2.  <span data-ttu-id="a719c-786">L’application d’annonce doit être déployée avec succès dans les pools ou serveurs de Lync source et de destination.</span><span class="sxs-lookup"><span data-stu-id="a719c-786">The announcement application has to be successfully deployed in the source and destination Lync Servers or Pools.</span></span>

<div>

## <a name="move-csannouncementconfiguration-script"></a><span data-ttu-id="a719c-787">Script Move-CsAnnouncementConfiguration</span><span class="sxs-lookup"><span data-stu-id="a719c-787">Move-CsAnnouncementConfiguration script</span></span>

<span data-ttu-id="a719c-788">Le script Move-CsAnnouncementConfiguration nécessite les deux paramètres décrits dans le tableau ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="a719c-788">The Move-CsAnnouncementConfiguration script requires the two parameters that are described in the table below.</span></span>

<span data-ttu-id="a719c-789">![Paramètres Move-CsAnnouncementConfiguration.](images/JJ945604.7ab66ad3-d0db-4d77-8b93-ebccf0cb0663(OCS.15).jpg "Paramètres Move-CsAnnouncementConfiguration.")</span><span class="sxs-lookup"><span data-stu-id="a719c-789">![Move-CsAnnouncementConfiguration parameters.](images/JJ945604.7ab66ad3-d0db-4d77-8b93-ebccf0cb0663(OCS.15).jpg "Move-CsAnnouncementConfiguration parameters.")</span></span>

</div>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="a719c-790">Exemples</span><span class="sxs-lookup"><span data-stu-id="a719c-790">Examples</span></span>

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2010-pool-to-a-lync-server-2013-pool"></a><span data-ttu-id="a719c-791">Transfert de la configuration des annonces de numéros non attribués à partir d’un pool Lync Server 2010 vers un pool Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a719c-791">Moving the Unassigned Number Announcements Configuration from a Lync Server 2010 Pool to a Lync Server 2013 Pool</span></span>

<span data-ttu-id="a719c-792">Cet exemple montre comment déplacer les annonces de numéros non attribués du pool source (Lync Server 2010) vers le pool de destination (Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="a719c-792">This example moves the unassigned number announcements from the source pool (Lync Server 2010) to the destination pool (Lync Server 2013).</span></span>

    Move-CsAnnouncementConfiguration.ps1 -Source LS2010Pool.contoso.com -Destination LS2013Pool.contoso.com

</div>

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-lync-server-2010-pool"></a><span data-ttu-id="a719c-793">Transfert de la configuration des annonces de numéros non attribués à partir d’un pool Lync Server 2013 vers un pool Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="a719c-793">Moving the Unassigned Number Announcements Configuration from a Lync Server 2013 Pool to a Lync Server 2010 Pool</span></span>

<span data-ttu-id="a719c-794">Cet exemple montre comment déplacer les annonces de numéros non attribués du pool source (Lync Server 2013) vers le pool de destination (Lync Server 2010).</span><span class="sxs-lookup"><span data-stu-id="a719c-794">This example moves the unassigned number announcements from the source pool (Lync Server 2013) to the destination pool (Lync Server 2010).</span></span>

    Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination LS2010Pool.contoso.com

</div>

</div>

</div>

<div>

## <a name="web-conf-data"></a><span data-ttu-id="a719c-795">Données Web CONF</span><span class="sxs-lookup"><span data-stu-id="a719c-795">Web Conf Data</span></span>

<span data-ttu-id="a719c-796">L’outil Web conf Data permet à un administrateur du logiciel de communication Lync Server 2013 de contrôler davantage les données associées aux conférences Web d’un organisateur.</span><span class="sxs-lookup"><span data-stu-id="a719c-796">The Web Conf Data Tool allows an administrator of Lync Server 2013 communications software to have more control over the data associated with an organizer’s Web conferences.</span></span> <span data-ttu-id="a719c-797">Les scénarios incluent la possibilité de supprimer les données de réunion d’un utilisateur spécifique en fonction de critères de date et d’heure.</span><span class="sxs-lookup"><span data-stu-id="a719c-797">Scenarios include the ability to delete a specific user’s meeting data based on a time stamp criteria.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="a719c-798">Description</span><span class="sxs-lookup"><span data-stu-id="a719c-798">Description</span></span>

<span data-ttu-id="a719c-799">Cet outil permet à l’administrateur d’effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="a719c-799">This tool allows the administrator to perform the following operations:</span></span>

1.  <span data-ttu-id="a719c-800">Rechercher toutes les données de conférence Web associées à un utilisateur unique.</span><span class="sxs-lookup"><span data-stu-id="a719c-800">Find all Web conferencing data associated with a single user.</span></span>

2.  <span data-ttu-id="a719c-801">Supprimer toutes les données de conférence Web associées à un utilisateur unique.</span><span class="sxs-lookup"><span data-stu-id="a719c-801">Delete all Web conferencing data associated with a single user.</span></span>

3.  <span data-ttu-id="a719c-802">Supprimer toutes les données de conférence Web associées à un seul utilisateur antérieur à une date donnée.</span><span class="sxs-lookup"><span data-stu-id="a719c-802">Delete all Web conferencing data associated with a single user that is older than a certain date.</span></span>

4.  <span data-ttu-id="a719c-803">Déplacer toutes les données de conférence Web associées à un seul utilisateur lorsque cet utilisateur est déplacé d’un pool vers un autre.</span><span class="sxs-lookup"><span data-stu-id="a719c-803">Move all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a719c-804">Les outils du kit de ressources pour Lync Server 2010 prennent en charge le déplacement de toutes les données de conférence Web associées à un utilisateur lorsque celui-ci est déplacé d’un pool vers un autre.</span><span class="sxs-lookup"><span data-stu-id="a719c-804">The Resource Kit Tools for Lync Server 2010 supported moving all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span> <span data-ttu-id="a719c-805">Cette fonctionnalité est désormais déconseillée de cet outil en faveur du paramètre <STRONG>MoveConferenceData</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="a719c-805">That functionality is now deprecated from this tool in favor of the <STRONG>MoveConferenceData</STRONG> parameter.</span></span> <span data-ttu-id="a719c-806">Pour plus d’informations sur ce paramètre, voir la cmdlet <A href="https://technet.microsoft.com/library/gg398528(v=ocs.15)">Move-Csuser</A> .</span><span class="sxs-lookup"><span data-stu-id="a719c-806">For details about this parameter, see the <A href="https://technet.microsoft.com/library/gg398528(v=ocs.15)">Move-CsUser</A> cmdlet.</span></span>



</div>

<span data-ttu-id="a719c-807">L’outil supprime les données de réunion uniquement pour les réunions inactives.</span><span class="sxs-lookup"><span data-stu-id="a719c-807">The tool deletes meeting data only for meetings that are inactive.</span></span> <span data-ttu-id="a719c-808">Les réunions actives (ou les réunions en session) ne peuvent pas être supprimées.</span><span class="sxs-lookup"><span data-stu-id="a719c-808">Active meetings (or meetings in sessions) cannot be deleted.</span></span>

<span data-ttu-id="a719c-809">Cet outil doit être exécuté à partir d’un ordinateur qui se trouve dans le même pool que l’utilisateur cible.</span><span class="sxs-lookup"><span data-stu-id="a719c-809">This tool must be run from a computer that is in the same pool as the target user.</span></span> <span data-ttu-id="a719c-810">L’utilisateur dont les données de contenu de réunion sont gérées par cet outil doit être hébergé dans le même pool d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a719c-810">The user whose meeting content data is being managed by this tool must be homed in the same user pool.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="a719c-811">Output</span><span class="sxs-lookup"><span data-stu-id="a719c-811">Output</span></span>

<span data-ttu-id="a719c-812">Cet outil renvoie les résultats de chacune des opérations :</span><span class="sxs-lookup"><span data-stu-id="a719c-812">This tool outputs the results of each of the operations:</span></span>

  - <span data-ttu-id="a719c-813">Si une requête est exécutée, l’outil génère la liste de tous les dossiers de données de réunion inactifs qui ont cet utilisateur comme organisateur.</span><span class="sxs-lookup"><span data-stu-id="a719c-813">If a query is performed, the tool outputs the list of all inactive meeting data folders that have that user as an organizer.</span></span>

  - <span data-ttu-id="a719c-814">Si une suppression est effectuée, l’outil génère la liste de tous les dossiers de données de réunion dont les données seront supprimées.</span><span class="sxs-lookup"><span data-stu-id="a719c-814">If a delete is performed, the tool outputs the list of all meeting data folders whose data will be deleted.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="a719c-815">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="a719c-815">Requirements</span></span>

<span data-ttu-id="a719c-816">L’outil doit être exécuté dans le même pool que l’organisateur.</span><span class="sxs-lookup"><span data-stu-id="a719c-816">The tool needs to be run in the same pool where the organizer is currently homed.</span></span>

<span data-ttu-id="a719c-817">L’outil doit être exécuté en utilisant les privilèges d’administrateur pour accéder au magasin de fichiers de contenu.</span><span class="sxs-lookup"><span data-stu-id="a719c-817">The tool must be run using administrator privileges with access to the Content File Store.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="a719c-818">Exemples</span><span class="sxs-lookup"><span data-stu-id="a719c-818">Examples</span></span>

<span data-ttu-id="a719c-819">Le tableau suivant décrit les paramètres, dont certains sont utilisés dans les exemples.</span><span class="sxs-lookup"><span data-stu-id="a719c-819">The following table describes the parameters, some of which are used in the examples.</span></span>

<span data-ttu-id="a719c-820">![Paramètres de l’outil Web conf Data.](images/JJ945604.a733c1c6-5dfc-4874-a74f-bfdee81c1401(OCS.15).jpg "Paramètres de l’outil Web conf Data.")</span><span class="sxs-lookup"><span data-stu-id="a719c-820">![Web Conf Data Tool parameters.](images/JJ945604.a733c1c6-5dfc-4874-a74f-bfdee81c1401(OCS.15).jpg "Web Conf Data Tool parameters.")</span></span>

    WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""

<span data-ttu-id="a719c-821">L’exemple précédent illustre le fonctionnement d’une commande de requête.</span><span class="sxs-lookup"><span data-stu-id="a719c-821">The preceding example shows how a query command would work.</span></span> <span data-ttu-id="a719c-822">La sortie de cette commande serait une liste de tous les dossiers de contenu de réunion qui seraient affectés par cet outil.</span><span class="sxs-lookup"><span data-stu-id="a719c-822">The output of such a command would be a list of all meeting content folders that would be affected by this tool.</span></span>

    WebConfDataTool.exe /User:user0@contoso.com /Action:delete

<span data-ttu-id="a719c-823">Le précédent est un exemple de commande Delete.</span><span class="sxs-lookup"><span data-stu-id="a719c-823">The preceding is an example of a delete command.</span></span> <span data-ttu-id="a719c-824">La commande Supprimer supprime tous les dossiers de réunion inactifs de cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a719c-824">The delete command will remove all inactive meeting folders from this user.</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="a719c-825">Résumé</span><span class="sxs-lookup"><span data-stu-id="a719c-825">Summary</span></span>

<span data-ttu-id="a719c-826">Cet outil peut être une ressource précieuse pour les administrateurs qui ont besoin d’un contrôle plus précis sur les données de réunion de conférence.</span><span class="sxs-lookup"><span data-stu-id="a719c-826">This tool can be a valuable resource to administrators who need more precise control over conference meeting data.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>
