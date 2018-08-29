---
title: Installer l’outil de planification dans Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/5/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
description: Avant de commencer la conception et planification de votre Skype pour Business Server 2015 infrastructure à l’aide de la Skype pour l’outil de planification de 2015 Business Server, vous devez d’abord installer l’outil de planification. L’outil de planification ne doit pas être déployé sur une station de travail ou un serveur faisant partie de l’infrastructure ou le domaine où vous prévoyez d’installer Skype pour Business Server 2015. Le fichier Readme qui accompagne l’outil de planification des détails des informations importantes sur l’installation et à l’aide de l’outil. Certaines des informations contenues dans le fichier Lisez-moi sont expliquées ici par souci de clarté.
ms.openlocfilehash: 2314a9ae548bea70bc13872714ae3215d7439eec
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23244322"
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a><span data-ttu-id="22afd-106">Installer l’outil de planification dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="22afd-106">Install the Planning Tool in Skype for Business Server 2015</span></span>

<span data-ttu-id="22afd-107">Avant de commencer la conception et planification de votre Skype pour Business Server 2015 infrastructure à l’aide de la Skype pour l’outil de planification de 2015 Business Server, vous devez d’abord installer l’outil de planification.</span><span class="sxs-lookup"><span data-stu-id="22afd-107">Before you begin designing and planning your Skype for Business Server 2015 infrastructure by using the Skype for Business Server 2015 Planning Tool, you must first install the Planning Tool.</span></span> <span data-ttu-id="22afd-108">L’outil de planification ne doit pas être déployé sur une station de travail ou un serveur faisant partie de l’infrastructure ou le domaine où vous prévoyez d’installer Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="22afd-108">The Planning Tool does not need to be deployed to a workstation or server that is part of the domain or infrastructure where you plan to install Skype for Business Server 2015.</span></span> <span data-ttu-id="22afd-109">Le fichier Readme qui accompagne l’outil de planification des détails des informations importantes sur l’installation et à l’aide de l’outil.</span><span class="sxs-lookup"><span data-stu-id="22afd-109">The Readme file that accompanies the Planning Tool details important information about installing and using the tool.</span></span> <span data-ttu-id="22afd-110">Certaines des informations contenues dans le fichier Lisez-moi sont expliquées ici par souci de clarté.</span><span class="sxs-lookup"><span data-stu-id="22afd-110">Some of the information in the Readme file is duplicated here for clarity.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="22afd-111">L’outil de planification doit être installé par un utilisateur disposant de droits d’administrateur et des autorisations sur l’ordinateur sur lequel l’outil doit être installé.</span><span class="sxs-lookup"><span data-stu-id="22afd-111">The Planning Tool requires installation by a user with administrator rights and permissions on the computer on which the tool is to be installed.</span></span>

<span data-ttu-id="22afd-112">Les systèmes d’exploitation pris en charge pour l’installation et l’utilisation de l’outil de planification sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="22afd-112">The supported operating systems for installation and operation of the Planning Tool are:</span></span>

- <span data-ttu-id="22afd-113">Windows 10</span><span class="sxs-lookup"><span data-stu-id="22afd-113">Windows 10</span></span>

- <span data-ttu-id="22afd-114">Windows 8</span><span class="sxs-lookup"><span data-stu-id="22afd-114">Windows 8</span></span>

- <span data-ttu-id="22afd-115">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="22afd-115">Windows 8.1</span></span>

- <span data-ttu-id="22afd-116">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="22afd-116">Windows Server 2012</span></span>

- <span data-ttu-id="22afd-117">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="22afd-117">Windows Server 2012 R2</span></span>

- <span data-ttu-id="22afd-118">Windows 7, édition 32 bits</span><span class="sxs-lookup"><span data-stu-id="22afd-118">Windows 7, 32-bit edition</span></span>

- <span data-ttu-id="22afd-119">Windows 7, édition 64 bits avec WOW (Windows on Win32)</span><span class="sxs-lookup"><span data-stu-id="22afd-119">Windows 7, 64-bit edition using Windows on Win32 (WOW)</span></span>

- <span data-ttu-id="22afd-120">Windows Server 2008 R2 avec WOW</span><span class="sxs-lookup"><span data-stu-id="22afd-120">Windows Server 2008 R2, using WOW</span></span>

<span data-ttu-id="22afd-121">En outre, l’outil de planification nécessite Microsoft .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="22afd-121">Additionally, the Planning Tool requires Microsoft .NET Framework 4.5.</span></span>

<span data-ttu-id="22afd-122">Une fois que les conditions de préinstallation sont remplies, vous pouvez ensuite installer l’outil de planification.</span><span class="sxs-lookup"><span data-stu-id="22afd-122">After the preinstallation requirements are met, you can then install the Planning Tool.</span></span>



## <a name="to-install-the-planning-tool"></a><span data-ttu-id="22afd-123">Pour installer l’outil de planification</span><span class="sxs-lookup"><span data-stu-id="22afd-123">To install the Planning Tool</span></span>

1. <span data-ttu-id="22afd-124">Ouvrez une session sur l’ordinateur local en tant que membre du groupe Administrateurs.</span><span class="sxs-lookup"><span data-stu-id="22afd-124">Log on to the local computer as a member of the Administrators group.</span></span>

2. <span data-ttu-id="22afd-125">À l’aide de l’Explorateur Windows ou une fenêtre de commande, recherchez le répertoire où vous avez téléchargé les fichiers d’installation de l’outil de planification.</span><span class="sxs-lookup"><span data-stu-id="22afd-125">Using Windows Explorer or a command window, locate the directory where you downloaded the Planning Tool installation files.</span></span>

3. <span data-ttu-id="22afd-p103">Recherchez le fichier SkypeForBusinessPlanningTool.msi. Dans l’Explorateur Windows, double-cliquez sur le fichier. Dans la fenêtre de commande, tapez le nom du fichier, puis appuyez sur **Entrée** pour exécuter le fichier.</span><span class="sxs-lookup"><span data-stu-id="22afd-p103">Locate the SkypeForBusinessPlanningTool.msi. In Windows Explorer, double-click the file. In the command window, type the name of the file, and then press **Enter** to run the file.</span></span>

4. <span data-ttu-id="22afd-129">Dans la page d’accueil de l’**Assistant Configuration de l’outil de planification de Skype Entreprise Server 2015**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="22afd-129">On the Welcome page of the **Skype for Business Server 2015, Planning Tool Setup Wizard**, click **Next**.</span></span>

5. <span data-ttu-id="22afd-130">Passez en revue le **Contrat de Licence Utilisateur Final**, sélectionnez **J’accepte les termes du contrat de licence** si vous choisissez d’accepter les termes d’utilisation contenus dans le contrat de licence, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="22afd-130">Review the **End-User License Agreement**, select **I accept the terms in the License Agreement** if you choose to accept the terms of use in the license agreement, and then click **Next**.</span></span>

6. <span data-ttu-id="22afd-p104">Choisissez où vous souhaitez installer les fichiers de l’outil de planification. L’emplacement d’installation par défaut est C:\Program Files (x86)\Skype for Business Server 2015\Planning Tool. Si vous souhaitez choisir un autre emplacement, cliquez sur **Modifier**. Dans **Modifier le dossier de destination**, accédez à l’emplacement d’installation des fichiers ou tapez-le directement dans le champ, cliquez sur **OK**, puis sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="22afd-p104">Choose where to install the Planning Tool files. The default location is C:\Program Files (x86)\Skype for Business Server 2015\Planning Tool. If you want to change the installation location, click **Change**. On **Change destination folder**, browse or type the location to install the files, click **OK**, and then click **Next**.</span></span>

7. <span data-ttu-id="22afd-135">Le programme d’installation est maintenant prêt à installer l’outil de planification.</span><span class="sxs-lookup"><span data-stu-id="22afd-135">The installer is now ready to install the Planning Tool.</span></span> <span data-ttu-id="22afd-136">Cliquez sur **Installer** pour commencer le processus d’installation.</span><span class="sxs-lookup"><span data-stu-id="22afd-136">Click **Install** to begin the installation process.</span></span>

8. <span data-ttu-id="22afd-p106">L’installation débute et la progression s’affiche. Une fois l’installation terminée, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="22afd-p106">The installation will start, and the progress will be displayed. After the installation is successfully completed, click **Finish**.</span></span>

9. <span data-ttu-id="22afd-139">L’outil de planification est prêt à être utilisé.</span><span class="sxs-lookup"><span data-stu-id="22afd-139">The Planning Tool is ready for use.</span></span>

## <a name="optional-software"></a><span data-ttu-id="22afd-140">Optional Software</span><span class="sxs-lookup"><span data-stu-id="22afd-140">Optional Software</span></span>
<span data-ttu-id="22afd-141"><a name="Optional_Software"> </a></span><span class="sxs-lookup"><span data-stu-id="22afd-141"></span></span>

<span data-ttu-id="22afd-142">Le Skype pour l’outil de planification de Business Server 2015 conçu pour l’exportation vers Microsoft Excel et Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="22afd-142">The Skype for Business Server 2015 Planning Tool is designed to export to Microsoft Excel and Microsoft Visio.</span></span> <span data-ttu-id="22afd-143">Alors que ces applications ne sont pas nécessaires au fonctionnement de l’outil de planification, ils ajoutent une valeur significative pour le déploiement et la documentation de votre conception.</span><span class="sxs-lookup"><span data-stu-id="22afd-143">While these applications are not required for the operation of the Planning Tool, they do add significant value to the deployment and documentation of your design.</span></span>

### <a name="microsoft-excel"></a><span data-ttu-id="22afd-144">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="22afd-144">Microsoft Excel</span></span>

<span data-ttu-id="22afd-145">L’exportation de votre conception vers Microsoft Excel permet de créer un rapport sous forme de feuille de calcul à quatre onglets :</span><span class="sxs-lookup"><span data-stu-id="22afd-145">Exporting your design to Microsoft Excel creates a report that displays seven tabs in the spreadsheet:</span></span>

- <span data-ttu-id="22afd-146">Résumé - affiche des informations sur la configuration du site, notamment le nombre d’utilisateurs, les paramètres de la capacité et les informations de profil de serveur.</span><span class="sxs-lookup"><span data-stu-id="22afd-146">Summary - Displays information on site configuration, including user count, capacity settings, and server profile information.</span></span>

- <span data-ttu-id="22afd-147">Profil matériel - affiche un rapport sur les configurations matérielle recommandée pour les serveurs qui sont spécifiés dans la topologie, y compris l’interface réseau, la mémoire, disque et processeur.</span><span class="sxs-lookup"><span data-stu-id="22afd-147">Hardware Profile - Displays a report on the recommended hardware configurations for servers that are specified in the topology, including CPU, memory, disk, and network interface.</span></span> <span data-ttu-id="22afd-148">La quantité et les caractéristiques conseillées pour les composants serveur y figurent également.</span><span class="sxs-lookup"><span data-stu-id="22afd-148">The quantity and recommended specifications for the server components are also included.</span></span> <span data-ttu-id="22afd-149">Par ailleurs, chaque serveur est défini par site afin de fournir une représentation complète de la configuration serveur requise pour chaque site.</span><span class="sxs-lookup"><span data-stu-id="22afd-149">In addition, each server is defined by site to provide a complete representation of server requirements by site.</span></span>

- <span data-ttu-id="22afd-150">Configuration requise des ports - affiche un rapport de tous les ports qui sont activés et l’association (DNS kg) d’équilibrage de charge de système de nom de domaine et les équilibreurs de charge matérielle (HLB).</span><span class="sxs-lookup"><span data-stu-id="22afd-150">Ports Requirements - Displays a report of all ports that are enabled, and the association to Domain Name System load balancing (DNS LB) and hardware load balancers (HLB).</span></span> <span data-ttu-id="22afd-151">Vous devez utiliser ce rapport pour planifier votre pare-feu et les configurations de l’équilibrage de la charge DNS et des programmes d’équilibrage de la charge matérielle.</span><span class="sxs-lookup"><span data-stu-id="22afd-151">You should use this report to plan your firewall and DNS LB and HLB configurations.</span></span>

- <span data-ttu-id="22afd-152">Rapport de synthèse - affiche le récapitulatif des paramètres qui sont nécessaires pour configurer votre réseau de serveur de transport Edge.</span><span class="sxs-lookup"><span data-stu-id="22afd-152">Summary Report - Displays the general summary of the settings that are required to set up your Edge Server network.</span></span>

- <span data-ttu-id="22afd-153">Rapport de certificats - affiche le nom du sujet et les autres noms du sujet qui sont requis pour les certificats nécessaires pour obtenir les serveurs de périphérie en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="22afd-153">Certificates Report - Displays the subject name and subject alternate names that are required for the certificates needed to get the Edge Servers running.</span></span>

- <span data-ttu-id="22afd-154">Rapport - affiche la source et destination des ports et adresses IP des interfaces interne et externe du pare-feu.</span><span class="sxs-lookup"><span data-stu-id="22afd-154">Firewall Report - Displays the source and destination ports and IP addresses for both External and Internal interfaces.</span></span>

- <span data-ttu-id="22afd-155">Rapport DNS - affiche le nom de domaine complet (FQDN) et les adresses IP/adresse IP virtuelle est requis pour chaque entrée DNS que vous créez.</span><span class="sxs-lookup"><span data-stu-id="22afd-155">DNS Report - Displays the fully qualified domain name (FQDN) and IP/VIP addresses required for each DNS entry that you create.</span></span>

### <a name="microsoft-visio"></a><span data-ttu-id="22afd-156">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="22afd-156">Microsoft Visio</span></span>

<span data-ttu-id="22afd-p110">L’exportation de votre conception vers Microsoft Visio crée un diagramme à utiliser dans la documentation de votre topologie et infrastructure configurée. Le diagramme importé peut être modifié et réorganisé pour répondre aux besoins de votre documentation. Un diagramme Visio classique inclut les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="22afd-p110">Exporting your design to Microsoft Visio creates a diagram for use in your documentation purposes of your configured topology and infrastructure. The imported diagram can be edited and rearranged to meet your documentation needs. The typical Visio diagram will include:</span></span>

> [!NOTE]
> <span data-ttu-id="22afd-160">Si votre conception est suffisante pour demander de plus de trois serveurs frontaux, une page supplémentaire sera créée pour le pool frontal, serveurs frontaux, l’ordinateur qui exécute SQL Server, les adresses IP et noms de domaine complets.</span><span class="sxs-lookup"><span data-stu-id="22afd-160">If your design is large enough to require more than three Front End Servers, an additional page will be created for the Front End pool, Front End Servers, the computer running SQL Server, IP addresses, and FQDNs.</span></span>

- <span data-ttu-id="22afd-161">Topologie globale : diagramme de Skype configuré pour les sites Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="22afd-161">Global Topology - Diagram of configured Skype for Business Server 2015 sites.</span></span>

- <span data-ttu-id="22afd-162">Onglet Nom de site - affiche la topologie de configuration de site avec le serveur de périphérie, le pare-feu, public switched téléphone PSTN (réseau) avec les passerelles et le déploiement du serveur interne.</span><span class="sxs-lookup"><span data-stu-id="22afd-162">Site Name tab - Displays the site configuration topology with Edge Server, firewall, public switched telephone network (PSTN) with gateways, and the internal server deployment.</span></span> <span data-ttu-id="22afd-163">Déploiement interne se compose de serveurs configurés et pools pools, y compris le serveur frontal, les serveurs SQL Server, Services de domaine Active Directory, directeurs, la messagerie unifiée Exchange (MU) serveurs, les serveurs de boîtes aux lettres Exchange, serveurs Office Web Apps Server, Serveurs de médiation et serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="22afd-163">Internal deployment consists of configured servers and pools, including the Front End pools, SQL Server-based servers, Active Directory Domain Services, Directors, Exchange Unified Messaging (UM) servers, Exchange Mailbox Servers, Office Web Apps Servers, Mediation Servers, and Persistent Chat Servers.</span></span>

- <span data-ttu-id="22afd-164">Edge organigramme - diagramme décrivant la configuration du serveur Edge avec associé à des adresses IP et noms de domaine complets.</span><span class="sxs-lookup"><span data-stu-id="22afd-164">Edge Network Diagram - Diagram detailing the Edge Server configuration with associated IP addresses and FQDNs.</span></span> <span data-ttu-id="22afd-165">L’équilibrage de la charge DNS et les programmes d’équilibrage de la charge matérielle sont également inclus.</span><span class="sxs-lookup"><span data-stu-id="22afd-165">DNS load balancing and hardware load balancers are also included.</span></span> <span data-ttu-id="22afd-166">En outre, les directeurs et le pool frontal ou serveur frontal sont affichés, avec kg de DNS associé ou matérielle et l’adresse IP (l’outil de planification prend en charge les adresses IPv4 et IPv6) et le nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="22afd-166">Additionally, Directors and the Front End Server or Front End pool are displayed, with associated DNS LB or HLB and the assigned IP address (the Planning Tool supports both IPv4 and IPv6 addresses) and FQDN.</span></span>

## <a name="see-also"></a><span data-ttu-id="22afd-167">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="22afd-167">See also</span></span>
<span data-ttu-id="22afd-168"><a name="Optional_Software"> </a></span><span class="sxs-lookup"><span data-stu-id="22afd-168"></span></span>

[<span data-ttu-id="22afd-169">Installation de l’outil de planification</span><span class="sxs-lookup"><span data-stu-id="22afd-169">Installing the Planning Tool</span></span>](https://technet.microsoft.com/library/ebdc9e26-4b22-4b02-85b9-7462bcfe7c93.aspx)