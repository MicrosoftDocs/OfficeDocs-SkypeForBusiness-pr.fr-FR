---
title: Installer l’outil de planification dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
description: Avant de commencer à concevoir et à planifier votre infrastructure 2015 de Skype entreprise Server à l’aide de l’outil de planification de Skype entreprise Server 2015, vous devez d’abord installer l’outil de planification. L’outil de planification n’a pas besoin d’être déployé vers une station de travail ou un serveur qui fait partie de l’infrastructure ou du domaine sur lequel vous envisagez d’installer Skype entreprise Server 2015. Le fichier Lisez-moi fourni avec les détails de l’outil de planification est une information importante sur son installation et son utilisation. Certaines des informations contenues dans le fichier Lisez-moi sont expliquées ici par souci de clarté.
ms.openlocfilehash: 192eae34bf6cf3fa53be82d8cb4450f960c90314
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279126"
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a><span data-ttu-id="376b1-106">Installer l’outil de planification dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="376b1-106">Install the Planning Tool in Skype for Business Server 2015</span></span>

<span data-ttu-id="376b1-107">Avant de commencer à concevoir et à planifier votre infrastructure 2015 de Skype entreprise Server à l’aide de l’outil de planification de Skype entreprise Server 2015, vous devez d’abord installer l’outil de planification.</span><span class="sxs-lookup"><span data-stu-id="376b1-107">Before you begin designing and planning your Skype for Business Server 2015 infrastructure by using the Skype for Business Server 2015 Planning Tool, you must first install the Planning Tool.</span></span> <span data-ttu-id="376b1-108">L’outil de planification n’a pas besoin d’être déployé vers une station de travail ou un serveur qui fait partie de l’infrastructure ou du domaine sur lequel vous envisagez d’installer Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="376b1-108">The Planning Tool does not need to be deployed to a workstation or server that is part of the domain or infrastructure where you plan to install Skype for Business Server 2015.</span></span> <span data-ttu-id="376b1-109">Le fichier Lisez-moi fourni avec les détails de l’outil de planification est une information importante sur son installation et son utilisation.</span><span class="sxs-lookup"><span data-stu-id="376b1-109">The Readme file that accompanies the Planning Tool details important information about installing and using the tool.</span></span> <span data-ttu-id="376b1-110">Certaines des informations contenues dans le fichier Lisez-moi sont expliquées ici par souci de clarté.</span><span class="sxs-lookup"><span data-stu-id="376b1-110">Some of the information in the Readme file is duplicated here for clarity.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="376b1-111">L’outil de planification nécessite une installation par un utilisateur disposant de droits d’administrateur et d’autorisations sur l’ordinateur sur lequel l’outil doit être installé.</span><span class="sxs-lookup"><span data-stu-id="376b1-111">The Planning Tool requires installation by a user with administrator rights and permissions on the computer on which the tool is to be installed.</span></span>

<span data-ttu-id="376b1-112">Les systèmes d’exploitation pris en charge pour l’installation et l’exécution de l’outil de planification sont les suivants:</span><span class="sxs-lookup"><span data-stu-id="376b1-112">The supported operating systems for installation and operation of the Planning Tool are:</span></span>

- <span data-ttu-id="376b1-113">Windows 10</span><span class="sxs-lookup"><span data-stu-id="376b1-113">Windows 10</span></span>

- <span data-ttu-id="376b1-114">Windows 8</span><span class="sxs-lookup"><span data-stu-id="376b1-114">Windows 8</span></span>

- <span data-ttu-id="376b1-115">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="376b1-115">Windows 8.1</span></span>

- <span data-ttu-id="376b1-116">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="376b1-116">Windows Server 2012</span></span>

- <span data-ttu-id="376b1-117">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="376b1-117">Windows Server 2012 R2</span></span>

- <span data-ttu-id="376b1-118">Windows 7, édition 32 bits</span><span class="sxs-lookup"><span data-stu-id="376b1-118">Windows 7, 32-bit edition</span></span>

- <span data-ttu-id="376b1-119">Windows 7, édition 64 bits avec WOW (Windows on Win32)</span><span class="sxs-lookup"><span data-stu-id="376b1-119">Windows 7, 64-bit edition using Windows on Win32 (WOW)</span></span>

- <span data-ttu-id="376b1-120">Windows Server 2008 R2 avec WOW</span><span class="sxs-lookup"><span data-stu-id="376b1-120">Windows Server 2008 R2, using WOW</span></span>

<span data-ttu-id="376b1-121">Par ailleurs, l’outil de planification nécessite Microsoft .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="376b1-121">Additionally, the Planning Tool requires Microsoft .NET Framework 4.5.</span></span>

<span data-ttu-id="376b1-122">Après avoir satisfait la configuration requise, vous pouvez ensuite installer l’outil de planification.</span><span class="sxs-lookup"><span data-stu-id="376b1-122">After the preinstallation requirements are met, you can then install the Planning Tool.</span></span>



## <a name="to-install-the-planning-tool"></a><span data-ttu-id="376b1-123">Pour installer l’outil de planification</span><span class="sxs-lookup"><span data-stu-id="376b1-123">To install the Planning Tool</span></span>

1. <span data-ttu-id="376b1-124">Connectez-vous à l’ordinateur local en tant que membre du groupe administrateurs.</span><span class="sxs-lookup"><span data-stu-id="376b1-124">Log on to the local computer as a member of the Administrators group.</span></span>

2. <span data-ttu-id="376b1-125">À l’aide de l’Explorateur Windows ou d’une fenêtre de commande, recherchez le répertoire dans lequel vous avez téléchargé les fichiers d’installation de l’outil de planification.</span><span class="sxs-lookup"><span data-stu-id="376b1-125">Using Windows Explorer or a command window, locate the directory where you downloaded the Planning Tool installation files.</span></span>

3. <span data-ttu-id="376b1-p103">Recherchez le fichier SkypeForBusinessPlanningTool.msi. Dans l’Explorateur Windows, double-cliquez sur le fichier. Dans la fenêtre de commande, tapez le nom du fichier, puis appuyez sur **Entrée** pour exécuter le fichier.</span><span class="sxs-lookup"><span data-stu-id="376b1-p103">Locate the SkypeForBusinessPlanningTool.msi. In Windows Explorer, double-click the file. In the command window, type the name of the file, and then press **Enter** to run the file.</span></span>

4. <span data-ttu-id="376b1-129">Dans la page d’accueil de l’**Assistant Configuration de l’outil de planification de Skype Entreprise Server 2015**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="376b1-129">On the Welcome page of the **Skype for Business Server 2015, Planning Tool Setup Wizard**, click **Next**.</span></span>

5. <span data-ttu-id="376b1-130">Passez en revue le **Contrat de Licence Utilisateur Final**, sélectionnez **J’accepte les termes du contrat de licence** si vous choisissez d’accepter les termes d’utilisation contenus dans le contrat de licence, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="376b1-130">Review the **End-User License Agreement**, select **I accept the terms in the License Agreement** if you choose to accept the terms of use in the license agreement, and then click **Next**.</span></span>

6. <span data-ttu-id="376b1-p104">Choisissez où vous souhaitez installer les fichiers de l’outil de planification. L’emplacement d’installation par défaut est C:\Program Files (x86)\Skype for Business Server 2015\Planning Tool. Si vous souhaitez choisir un autre emplacement, cliquez sur **Modifier**. Dans **Modifier le dossier de destination**, accédez à l’emplacement d’installation des fichiers ou tapez-le directement dans le champ, cliquez sur **OK**, puis sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="376b1-p104">Choose where to install the Planning Tool files. The default location is C:\Program Files (x86)\Skype for Business Server 2015\Planning Tool. If you want to change the installation location, click **Change**. On **Change destination folder**, browse or type the location to install the files, click **OK**, and then click **Next**.</span></span>

7. <span data-ttu-id="376b1-135">Le programme d’installation est désormais prêt à installer l’outil de planification.</span><span class="sxs-lookup"><span data-stu-id="376b1-135">The installer is now ready to install the Planning Tool.</span></span> <span data-ttu-id="376b1-136">Cliquez sur **Installer** pour commencer le processus d’installation.</span><span class="sxs-lookup"><span data-stu-id="376b1-136">Click **Install** to begin the installation process.</span></span>

8. <span data-ttu-id="376b1-137">L’installation débute et la progression s’affiche.</span><span class="sxs-lookup"><span data-stu-id="376b1-137">The installation will start, and the progress will be displayed.</span></span> <span data-ttu-id="376b1-138">Une fois l’installation terminée, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="376b1-138">After the installation is successfully completed, click **Finish**.</span></span>

9. <span data-ttu-id="376b1-139">L’outil de planification est prêt à l’emploi.</span><span class="sxs-lookup"><span data-stu-id="376b1-139">The Planning Tool is ready for use.</span></span>

## <a name="optional-software"></a><span data-ttu-id="376b1-140">Logiciels facultatifs</span><span class="sxs-lookup"><span data-stu-id="376b1-140">Optional Software</span></span>
<span data-ttu-id="376b1-141"><a name="Optional_Software"> </a></span><span class="sxs-lookup"><span data-stu-id="376b1-141"></span></span>

<span data-ttu-id="376b1-142">L’outil de planification de Skype entreprise Server 2015 est conçu pour être exporté vers Microsoft Excel et Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="376b1-142">The Skype for Business Server 2015 Planning Tool is designed to export to Microsoft Excel and Microsoft Visio.</span></span> <span data-ttu-id="376b1-143">Même si ces applications ne sont pas nécessaires pour l’utilisation de l’outil de planification, elles ajoutent une valeur importante au déploiement et à la documentation de votre conception.</span><span class="sxs-lookup"><span data-stu-id="376b1-143">While these applications are not required for the operation of the Planning Tool, they do add significant value to the deployment and documentation of your design.</span></span>

### <a name="microsoft-excel"></a><span data-ttu-id="376b1-144">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="376b1-144">Microsoft Excel</span></span>

<span data-ttu-id="376b1-145">L’exportation de votre conception vers Microsoft Excel permet de créer un rapport sous forme de feuille de calcul à quatre onglets :</span><span class="sxs-lookup"><span data-stu-id="376b1-145">Exporting your design to Microsoft Excel creates a report that displays seven tabs in the spreadsheet:</span></span>

- <span data-ttu-id="376b1-146">Résumé: affiche des informations sur la configuration du site, dont le nombre d’utilisateurs, les paramètres de capacité et les informations de profil du serveur.</span><span class="sxs-lookup"><span data-stu-id="376b1-146">Summary - Displays information on site configuration, including user count, capacity settings, and server profile information.</span></span>

- <span data-ttu-id="376b1-147">Profil matériel-affiche un rapport sur les configurations matérielles recommandées pour les serveurs spécifiés dans la topologie, dont l’UC, la mémoire, le disque et l’interface réseau.</span><span class="sxs-lookup"><span data-stu-id="376b1-147">Hardware Profile - Displays a report on the recommended hardware configurations for servers that are specified in the topology, including CPU, memory, disk, and network interface.</span></span> <span data-ttu-id="376b1-148">La quantité et les caractéristiques conseillées pour les composants serveur y figurent également.</span><span class="sxs-lookup"><span data-stu-id="376b1-148">The quantity and recommended specifications for the server components are also included.</span></span> <span data-ttu-id="376b1-149">Par ailleurs, chaque serveur est défini par site afin de fournir une représentation complète de la configuration serveur requise pour chaque site.</span><span class="sxs-lookup"><span data-stu-id="376b1-149">In addition, each server is defined by site to provide a complete representation of server requirements by site.</span></span>

- <span data-ttu-id="376b1-150">Configuration requise pour les ports: affiche un rapport de tous les ports activés, ainsi que l’Association au service d’équilibrage de la charge de DNS (Domain Name System) et des équilibreurs de charge matérielle (HLB).</span><span class="sxs-lookup"><span data-stu-id="376b1-150">Ports Requirements - Displays a report of all ports that are enabled, and the association to Domain Name System load balancing (DNS LB) and hardware load balancers (HLB).</span></span> <span data-ttu-id="376b1-151">Vous devez utiliser ce rapport pour planifier votre pare-feu et les configurations de l’équilibrage de la charge DNS et des programmes d’équilibrage de la charge matérielle.</span><span class="sxs-lookup"><span data-stu-id="376b1-151">You should use this report to plan your firewall and DNS LB and HLB configurations.</span></span>

- <span data-ttu-id="376b1-152">Rapport de synthèse: affiche la synthèse générale des paramètres nécessaires à la configuration de votre réseau Edge Server.</span><span class="sxs-lookup"><span data-stu-id="376b1-152">Summary Report - Displays the general summary of the settings that are required to set up your Edge Server network.</span></span>

- <span data-ttu-id="376b1-153">Rapport sur les certificats: affiche le nom du sujet et les noms de domaine alternatif requis pour les certificats nécessaires à l’exécution des serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="376b1-153">Certificates Report - Displays the subject name and subject alternate names that are required for the certificates needed to get the Edge Servers running.</span></span>

- <span data-ttu-id="376b1-154">Rapport de pare-feu-affiche les ports et adresses IP sources et de destination pour les interfaces internes et externes.</span><span class="sxs-lookup"><span data-stu-id="376b1-154">Firewall Report - Displays the source and destination ports and IP addresses for both External and Internal interfaces.</span></span>

- <span data-ttu-id="376b1-155">Rapport DNS-affiche le nom de domaine complet (FQDN) et les adresses IP/VIP requises pour chaque entrée DNS que vous créez.</span><span class="sxs-lookup"><span data-stu-id="376b1-155">DNS Report - Displays the fully qualified domain name (FQDN) and IP/VIP addresses required for each DNS entry that you create.</span></span>

### <a name="microsoft-visio"></a><span data-ttu-id="376b1-156">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="376b1-156">Microsoft Visio</span></span>

<span data-ttu-id="376b1-p110">L’exportation de votre conception vers Microsoft Visio crée un diagramme à utiliser dans la documentation de votre topologie et infrastructure configurée. Le diagramme importé peut être modifié et réorganisé pour répondre aux besoins de votre documentation. Un diagramme Visio classique inclut les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="376b1-p110">Exporting your design to Microsoft Visio creates a diagram for use in your documentation purposes of your configured topology and infrastructure. The imported diagram can be edited and rearranged to meet your documentation needs. The typical Visio diagram will include:</span></span>

> [!NOTE]
> <span data-ttu-id="376b1-160">Si votre conception est suffisamment grande pour nécessiter plus de trois serveurs frontaux, une page supplémentaire est créée pour le pool frontal, les serveurs frontaux, l’ordinateur exécutant SQL Server, les adresses IP et les noms de domaine complets.</span><span class="sxs-lookup"><span data-stu-id="376b1-160">If your design is large enough to require more than three Front End Servers, an additional page will be created for the Front End pool, Front End Servers, the computer running SQL Server, IP addresses, and FQDNs.</span></span>

- <span data-ttu-id="376b1-161">Topologie globale: diagramme des sites 2015 Skype entreprise Server configurés.</span><span class="sxs-lookup"><span data-stu-id="376b1-161">Global Topology - Diagram of configured Skype for Business Server 2015 sites.</span></span>

- <span data-ttu-id="376b1-162">Onglet nom du site: affiche la topologie de configuration de site avec serveur de périmètre, pare-feu, réseau téléphonique public commuté (RTC) avec passerelles et le déploiement de serveur interne.</span><span class="sxs-lookup"><span data-stu-id="376b1-162">Site Name tab - Displays the site configuration topology with Edge Server, firewall, public switched telephone network (PSTN) with gateways, and the internal server deployment.</span></span> <span data-ttu-id="376b1-163">Le déploiement interne se compose de serveurs et de pools configurés, y compris les pools front end, serveurs SQL Server, services de domaine Active Directory, directeurs, serveurs de messagerie unifiée Exchange, serveurs de boîte aux lettres Exchange, serveurs Office Web Apps. Serveurs de médiation et serveurs de chat permanents.</span><span class="sxs-lookup"><span data-stu-id="376b1-163">Internal deployment consists of configured servers and pools, including the Front End pools, SQL Server-based servers, Active Directory Domain Services, Directors, Exchange Unified Messaging (UM) servers, Exchange Mailbox Servers, Office Web Apps Servers, Mediation Servers, and Persistent Chat Servers.</span></span>

- <span data-ttu-id="376b1-164">Diagramme de réseau Edge-schéma de détails de la configuration du serveur de périphérie avec adresses IP et noms de domaine complets associés.</span><span class="sxs-lookup"><span data-stu-id="376b1-164">Edge Network Diagram - Diagram detailing the Edge Server configuration with associated IP addresses and FQDNs.</span></span> <span data-ttu-id="376b1-165">L’équilibrage de la charge DNS et les programmes d’équilibrage de la charge matérielle sont également inclus.</span><span class="sxs-lookup"><span data-stu-id="376b1-165">DNS load balancing and hardware load balancers are also included.</span></span> <span data-ttu-id="376b1-166">De plus, les directeurs et le serveur frontal ou le pool frontal sont affichés, avec DNS ou HLB associé et l’adresse IP attribuée (l’outil de planification prend en charge à la fois les adresses IPv4 et IPv6) et le FQDN.</span><span class="sxs-lookup"><span data-stu-id="376b1-166">Additionally, Directors and the Front End Server or Front End pool are displayed, with associated DNS LB or HLB and the assigned IP address (the Planning Tool supports both IPv4 and IPv6 addresses) and FQDN.</span></span>

## <a name="see-also"></a><span data-ttu-id="376b1-167">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="376b1-167">See also</span></span>
<span data-ttu-id="376b1-168"><a name="Optional_Software"> </a></span><span class="sxs-lookup"><span data-stu-id="376b1-168"></span></span>

[<span data-ttu-id="376b1-169">Installing the Planning Tool</span><span class="sxs-lookup"><span data-stu-id="376b1-169">Installing the Planning Tool</span></span>](https://technet.microsoft.com/library/ebdc9e26-4b22-4b02-85b9-7462bcfe7c93.aspx)
