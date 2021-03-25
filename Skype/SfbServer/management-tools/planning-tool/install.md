---
title: Installer l’outil de planification dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
description: Avant de commencer à concevoir et planifier votre infrastructure Skype Entreprise Server 2015 à l’aide de l’outil de planification de Skype Entreprise Server 2015, vous devez d’abord installer l’outil de planification. L’outil de planification n’a pas besoin d’être déployé sur une station de travail ou un serveur qui fait partie du domaine ou de l’infrastructure où vous prévoyez d’installer Skype Entreprise Server 2015. Le fichier Lisez-moi qui accompagne l’outil de planification détaille des informations importantes sur l’installation et l’utilisation de l’outil. Certaines informations du fichier Lisez-moi sont dupliquées ici pour plus de clarté.
ms.openlocfilehash: 29a3bd35191cf326cafd1f4ad4f14fab50e47ea3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122378"
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a><span data-ttu-id="144e0-106">Installer l’outil de planification dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="144e0-106">Install the Planning Tool in Skype for Business Server 2015</span></span>

<span data-ttu-id="144e0-107">Avant de commencer à concevoir et planifier votre infrastructure Skype Entreprise Server 2015 à l’aide de l’outil de planification de Skype Entreprise Server 2015, vous devez d’abord installer l’outil de planification.</span><span class="sxs-lookup"><span data-stu-id="144e0-107">Before you begin designing and planning your Skype for Business Server 2015 infrastructure by using the Skype for Business Server 2015 Planning Tool, you must first install the Planning Tool.</span></span> <span data-ttu-id="144e0-108">L’outil de planification n’a pas besoin d’être déployé sur une station de travail ou un serveur qui fait partie du domaine ou de l’infrastructure où vous prévoyez d’installer Skype Entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="144e0-108">The Planning Tool does not need to be deployed to a workstation or server that is part of the domain or infrastructure where you plan to install Skype for Business Server 2015.</span></span> <span data-ttu-id="144e0-109">Le fichier Lisez-moi qui accompagne l’outil de planification détaille des informations importantes sur l’installation et l’utilisation de l’outil.</span><span class="sxs-lookup"><span data-stu-id="144e0-109">The Readme file that accompanies the Planning Tool details important information about installing and using the tool.</span></span> <span data-ttu-id="144e0-110">Certaines informations du fichier Lisez-moi sont dupliquées ici pour plus de clarté.</span><span class="sxs-lookup"><span data-stu-id="144e0-110">Some of the information in the Readme file is duplicated here for clarity.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="144e0-111">L’outil de planification nécessite l’installation par un utilisateur ayant des droits et des autorisations d’administrateur sur l’ordinateur sur lequel l’outil doit être installé.</span><span class="sxs-lookup"><span data-stu-id="144e0-111">The Planning Tool requires installation by a user with administrator rights and permissions on the computer on which the tool is to be installed.</span></span>

<span data-ttu-id="144e0-112">Les systèmes d’exploitation pris en charge pour l’installation et le fonctionnement de l’outil de planification sont :</span><span class="sxs-lookup"><span data-stu-id="144e0-112">The supported operating systems for installation and operation of the Planning Tool are:</span></span>

- <span data-ttu-id="144e0-113">Windows 10</span><span class="sxs-lookup"><span data-stu-id="144e0-113">Windows 10</span></span>

- <span data-ttu-id="144e0-114">Windows 8</span><span class="sxs-lookup"><span data-stu-id="144e0-114">Windows 8</span></span>

- <span data-ttu-id="144e0-115">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="144e0-115">Windows 8.1</span></span>

- <span data-ttu-id="144e0-116">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="144e0-116">Windows Server 2012</span></span>

- <span data-ttu-id="144e0-117">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="144e0-117">Windows Server 2012 R2</span></span>

- <span data-ttu-id="144e0-118">Windows 7, édition 32 bits</span><span class="sxs-lookup"><span data-stu-id="144e0-118">Windows 7, 32-bit edition</span></span>

- <span data-ttu-id="144e0-119">Windows 7, édition 64 bits utilisant Windows sur Win32 (WOW)</span><span class="sxs-lookup"><span data-stu-id="144e0-119">Windows 7, 64-bit edition using Windows on Win32 (WOW)</span></span>

- <span data-ttu-id="144e0-120">Windows Server 2008 R2, à l’aide de WOW</span><span class="sxs-lookup"><span data-stu-id="144e0-120">Windows Server 2008 R2, using WOW</span></span>

<span data-ttu-id="144e0-121">En outre, l’outil de planification nécessite Microsoft .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="144e0-121">Additionally, the Planning Tool requires Microsoft .NET Framework 4.5.</span></span>

<span data-ttu-id="144e0-122">Une fois que les conditions de préinstallation sont remplies, vous pouvez installer l’outil de planification.</span><span class="sxs-lookup"><span data-stu-id="144e0-122">After the preinstallation requirements are met, you can then install the Planning Tool.</span></span>



## <a name="to-install-the-planning-tool"></a><span data-ttu-id="144e0-123">Pour installer l’outil de planification</span><span class="sxs-lookup"><span data-stu-id="144e0-123">To install the Planning Tool</span></span>

1. <span data-ttu-id="144e0-124">Ouvrez une session sur l’ordinateur local en tant que membre du groupe Administrateurs.</span><span class="sxs-lookup"><span data-stu-id="144e0-124">Log on to the local computer as a member of the Administrators group.</span></span>

2. <span data-ttu-id="144e0-125">À l’aide de l’Explorateur Windows ou d’une fenêtre de commande, recherchez le répertoire dans lequel vous avez téléchargé les fichiers d’installation de l’outil de planification.</span><span class="sxs-lookup"><span data-stu-id="144e0-125">Using Windows Explorer or a command window, locate the directory where you downloaded the Planning Tool installation files.</span></span>

3. <span data-ttu-id="144e0-126">Recherchez le SkypeForBusinessPlanningTool.msi.</span><span class="sxs-lookup"><span data-stu-id="144e0-126">Locate the SkypeForBusinessPlanningTool.msi.</span></span> <span data-ttu-id="144e0-127">Dans l’Explorateur Windows, double-cliquez sur le fichier.</span><span class="sxs-lookup"><span data-stu-id="144e0-127">In Windows Explorer, double-click the file.</span></span> <span data-ttu-id="144e0-128">Dans la fenêtre de commande, tapez le nom du fichier, puis appuyez sur **Entrée** pour exécuter le fichier.</span><span class="sxs-lookup"><span data-stu-id="144e0-128">In the command window, type the name of the file, and then press **Enter** to run the file.</span></span>

4. <span data-ttu-id="144e0-129">Dans la page d’accueil de **Skype Entreprise Server 2015,** Assistant Configuration de l’outil de planification, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="144e0-129">On the Welcome page of the **Skype for Business Server 2015, Planning Tool Setup Wizard**, click **Next**.</span></span>

5. <span data-ttu-id="144e0-130">Consultez **le contrat** de licence utilisateur final, sélectionnez J’accepte les termes du contrat de licence si vous choisissez d’accepter les conditions d’utilisation dans le contrat de licence, puis cliquez sur **Suivant**. </span><span class="sxs-lookup"><span data-stu-id="144e0-130">Review the **End-User License Agreement**, select **I accept the terms in the License Agreement** if you choose to accept the terms of use in the license agreement, and then click **Next**.</span></span>

6. <span data-ttu-id="144e0-131">Choisissez l’endroit où installer les fichiers de l’outil de planification.</span><span class="sxs-lookup"><span data-stu-id="144e0-131">Choose where to install the Planning Tool files.</span></span> <span data-ttu-id="144e0-132">L’emplacement par défaut est C:\Program Files (x86)\Skype for Business Server 2015\Planning Tool.</span><span class="sxs-lookup"><span data-stu-id="144e0-132">The default location is C:\Program Files (x86)\Skype for Business Server 2015\Planning Tool.</span></span> <span data-ttu-id="144e0-133">Si vous souhaitez modifier l’emplacement d’installation, cliquez sur **Modifier.**</span><span class="sxs-lookup"><span data-stu-id="144e0-133">If you want to change the installation location, click **Change**.</span></span> <span data-ttu-id="144e0-134">Sur **Modifier le dossier de destination,** parcourez ou tapez l’emplacement d’installation des fichiers, cliquez sur **OK,** puis sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="144e0-134">On **Change destination folder**, browse or type the location to install the files, click **OK**, and then click **Next**.</span></span>

7. <span data-ttu-id="144e0-135">Le programme d’installation est maintenant prêt à installer l’outil de planification.</span><span class="sxs-lookup"><span data-stu-id="144e0-135">The installer is now ready to install the Planning Tool.</span></span> <span data-ttu-id="144e0-136">Cliquez **sur Installer** pour commencer le processus d’installation.</span><span class="sxs-lookup"><span data-stu-id="144e0-136">Click **Install** to begin the installation process.</span></span>

8. <span data-ttu-id="144e0-137">L’installation démarre et la progression s’affiche.</span><span class="sxs-lookup"><span data-stu-id="144e0-137">The installation will start, and the progress will be displayed.</span></span> <span data-ttu-id="144e0-138">Une fois l’installation terminée, cliquez sur **Terminer.**</span><span class="sxs-lookup"><span data-stu-id="144e0-138">After the installation is successfully completed, click **Finish**.</span></span>

9. <span data-ttu-id="144e0-139">L’outil de planification est prêt à être utilisé.</span><span class="sxs-lookup"><span data-stu-id="144e0-139">The Planning Tool is ready for use.</span></span>

## <a name="optional-software"></a><span data-ttu-id="144e0-140">Logiciels facultatifs</span><span class="sxs-lookup"><span data-stu-id="144e0-140">Optional Software</span></span>
<span data-ttu-id="144e0-141"><a name="Optional_Software"> </a></span><span class="sxs-lookup"><span data-stu-id="144e0-141"><a name="Optional_Software"> </a></span></span>

<span data-ttu-id="144e0-142">L’outil de planification de Skype Entreprise Server 2015 est conçu pour exporter vers Microsoft Excel et Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="144e0-142">The Skype for Business Server 2015 Planning Tool is designed to export to Microsoft Excel and Microsoft Visio.</span></span> <span data-ttu-id="144e0-143">Bien que ces applications ne soient pas requises pour le fonctionnement de l’outil de planification, elles ajoutent une valeur significative au déploiement et à la documentation de votre conception.</span><span class="sxs-lookup"><span data-stu-id="144e0-143">While these applications are not required for the operation of the Planning Tool, they do add significant value to the deployment and documentation of your design.</span></span>

### <a name="microsoft-excel"></a><span data-ttu-id="144e0-144">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="144e0-144">Microsoft Excel</span></span>

<span data-ttu-id="144e0-145">L’exportation de votre conception vers Microsoft Excel crée un rapport qui affiche sept onglets dans la feuille de calcul :</span><span class="sxs-lookup"><span data-stu-id="144e0-145">Exporting your design to Microsoft Excel creates a report that displays seven tabs in the spreadsheet:</span></span>

- <span data-ttu-id="144e0-146">Résumé : affiche des informations sur la configuration du site, notamment le nombre d’utilisateurs, les paramètres de capacité et les informations de profil de serveur.</span><span class="sxs-lookup"><span data-stu-id="144e0-146">Summary - Displays information on site configuration, including user count, capacity settings, and server profile information.</span></span>

- <span data-ttu-id="144e0-147">Profil matériel : affiche un rapport sur les configurations matérielles recommandées pour les serveurs spécifiés dans la topologie, y compris le processeur, la mémoire, le disque et l’interface réseau.</span><span class="sxs-lookup"><span data-stu-id="144e0-147">Hardware Profile - Displays a report on the recommended hardware configurations for servers that are specified in the topology, including CPU, memory, disk, and network interface.</span></span> <span data-ttu-id="144e0-148">La quantité et les spécifications recommandées pour les composants serveur sont également incluses.</span><span class="sxs-lookup"><span data-stu-id="144e0-148">The quantity and recommended specifications for the server components are also included.</span></span> <span data-ttu-id="144e0-149">En outre, chaque serveur est défini par site pour fournir une représentation complète des besoins du serveur par site.</span><span class="sxs-lookup"><span data-stu-id="144e0-149">In addition, each server is defined by site to provide a complete representation of server requirements by site.</span></span>

- <span data-ttu-id="144e0-150">Configuration requise pour les ports : affiche un rapport de tous les ports activés, ainsi que l’association à l’équilibrage de la charge DNS (Domain Name System) et aux équilibreurs de charge matérielle (HLB).</span><span class="sxs-lookup"><span data-stu-id="144e0-150">Ports Requirements - Displays a report of all ports that are enabled, and the association to Domain Name System load balancing (DNS LB) and hardware load balancers (HLB).</span></span> <span data-ttu-id="144e0-151">Vous devez utiliser ce rapport pour planifier votre pare-feu et les configurations DNS LB et HLB.</span><span class="sxs-lookup"><span data-stu-id="144e0-151">You should use this report to plan your firewall and DNS LB and HLB configurations.</span></span>

- <span data-ttu-id="144e0-152">Rapport de synthèse : affiche le résumé général des paramètres requis pour configurer votre réseau de serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="144e0-152">Summary Report - Displays the general summary of the settings that are required to set up your Edge Server network.</span></span>

- <span data-ttu-id="144e0-153">Rapport sur les certificats : affiche le nom du sujet et les autres noms du sujet requis pour les certificats nécessaires à l’exécution des serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="144e0-153">Certificates Report - Displays the subject name and subject alternate names that are required for the certificates needed to get the Edge Servers running.</span></span>

- <span data-ttu-id="144e0-154">Rapport de pare-feu : affiche les ports source et de destination et les adresses IP des interfaces externe et interne.</span><span class="sxs-lookup"><span data-stu-id="144e0-154">Firewall Report - Displays the source and destination ports and IP addresses for both External and Internal interfaces.</span></span>

- <span data-ttu-id="144e0-155">Rapport DNS : affiche le nom de domaine complet (FQDN) et les adresses IP/VIP requises pour chaque entrée DNS que vous créez.</span><span class="sxs-lookup"><span data-stu-id="144e0-155">DNS Report - Displays the fully qualified domain name (FQDN) and IP/VIP addresses required for each DNS entry that you create.</span></span>

### <a name="microsoft-visio"></a><span data-ttu-id="144e0-156">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="144e0-156">Microsoft Visio</span></span>

<span data-ttu-id="144e0-p110">L’exportation de votre conception vers Microsoft Visio crée un diagramme à utiliser dans la documentation de votre topologie et infrastructure configurée. Le diagramme importé peut être modifié et réorganisé pour répondre aux besoins de votre documentation. Un diagramme Visio classique inclut les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="144e0-p110">Exporting your design to Microsoft Visio creates a diagram for use in your documentation purposes of your configured topology and infrastructure. The imported diagram can be edited and rearranged to meet your documentation needs. The typical Visio diagram will include:</span></span>

> [!NOTE]
> <span data-ttu-id="144e0-160">Si votre conception est suffisamment grande pour nécessiter plus de trois serveurs frontaux, une page supplémentaire est créée pour le pool frontal, les serveurs frontaux, l’ordinateur exécutant SQL Server, les adresses IP et les noms de famille.</span><span class="sxs-lookup"><span data-stu-id="144e0-160">If your design is large enough to require more than three Front End Servers, an additional page will be created for the Front End pool, Front End Servers, the computer running SQL Server, IP addresses, and FQDNs.</span></span>

- <span data-ttu-id="144e0-161">Topologie globale : diagramme des sites Skype Entreprise Server 2015 configurés.</span><span class="sxs-lookup"><span data-stu-id="144e0-161">Global Topology - Diagram of configured Skype for Business Server 2015 sites.</span></span>

- <span data-ttu-id="144e0-162">Onglet Nom du site : affiche la topologie de configuration du site avec le serveur Edge, le pare-feu, le réseau téléphonique commuté (PSTN) avec passerelles et le déploiement de serveur interne.</span><span class="sxs-lookup"><span data-stu-id="144e0-162">Site Name tab - Displays the site configuration topology with Edge Server, firewall, public switched telephone network (PSTN) with gateways, and the internal server deployment.</span></span> <span data-ttu-id="144e0-163">Le déploiement interne se compose de serveurs et de pools configurés, notamment les pools frontaux, les serveurs basés sur SQL Server, les services de domaine Active Directory, les directeurs, les serveurs de messagerie unifiée Exchange, les serveurs de boîtes aux lettres Exchange, les serveurs Office Web Apps, les serveurs de médiation et les serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="144e0-163">Internal deployment consists of configured servers and pools, including the Front End pools, SQL Server-based servers, Active Directory Domain Services, Directors, Exchange Unified Messaging (UM) servers, Exchange Mailbox Servers, Office Web Apps Servers, Mediation Servers, and Persistent Chat Servers.</span></span>

- <span data-ttu-id="144e0-164">Diagramme du réseau de périphérie : diagramme détaillant la configuration du serveur Edge avec les adresses IP et les noms de noms de serveur (FQDN) associés.</span><span class="sxs-lookup"><span data-stu-id="144e0-164">Edge Network Diagram - Diagram detailing the Edge Server configuration with associated IP addresses and FQDNs.</span></span> <span data-ttu-id="144e0-165">L’équilibrage de charge DNS et les programmes d’équilibrage de la charge matérielle sont également inclus.</span><span class="sxs-lookup"><span data-stu-id="144e0-165">DNS load balancing and hardware load balancers are also included.</span></span> <span data-ttu-id="144e0-166">En outre, les directeurs et le serveur frontal ou le pool frontal sont affichés, avec LB ou HLB DNS associé et l’adresse IP affectée (l’outil de planification prend en charge les adresses IPv4 et IPv6) et le nom deqdn.</span><span class="sxs-lookup"><span data-stu-id="144e0-166">Additionally, Directors and the Front End Server or Front End pool are displayed, with associated DNS LB or HLB and the assigned IP address (the Planning Tool supports both IPv4 and IPv6 addresses) and FQDN.</span></span>

## <a name="see-also"></a><span data-ttu-id="144e0-167">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="144e0-167">See also</span></span>
<span data-ttu-id="144e0-168"><a name="Optional_Software"> </a></span><span class="sxs-lookup"><span data-stu-id="144e0-168"><a name="Optional_Software"> </a></span></span>

[<span data-ttu-id="144e0-169">Installation de l’outil de planification</span><span class="sxs-lookup"><span data-stu-id="144e0-169">Installing the Planning Tool</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-installing-the-planning-tool)