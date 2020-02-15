---
title: 'Lync Server 2013 : outils d’administration Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server administrative tools
ms:assetid: 9b006f93-4f3d-461d-89b8-e80a34fdb3c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195756(v=OCS.15)
ms:contentKeyID: 48184972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f6de54e91129351a153c9cf4e08925d62eeb342c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030237"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-administrative-tools"></a><span data-ttu-id="78d96-102">Outils d’administration Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78d96-102">Lync Server 2013 administrative tools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78d96-103">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="78d96-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="78d96-104">Cette rubrique décrit les outils d’administration de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="78d96-104">This topic describes the administrative tools for Lync Server 2013.</span></span>

<span data-ttu-id="78d96-105">Les outils d’administration sont installés par défaut sur chaque serveur Lync Server.</span><span class="sxs-lookup"><span data-stu-id="78d96-105">The administrative tools are installed by default on each Lync Server server.</span></span> <span data-ttu-id="78d96-106">Vous pouvez également les installer sur d’autres ordinateurs, notamment des consoles d’administration dédiées.</span><span class="sxs-lookup"><span data-stu-id="78d96-106">Additionally, you can install the administrative tools on other computers, such as dedicated administrative consoles.</span></span> <span data-ttu-id="78d96-107">Pour connaître les procédures d’installation des outils d’administration, reportez-vous à la rubrique [install Lync Server 2013 administrative Tools](lync-server-2013-install-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="78d96-107">For procedures to install the administrative tools, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span> <span data-ttu-id="78d96-108">Pour connaître les procédures permettant d’ouvrir les outils permettant d’effectuer des tâches de gestion, reportez-vous à la rubrique [Open Lync Server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="78d96-108">For procedures to open the tools to perform management tasks, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

<span data-ttu-id="78d96-109">Avant d’installer ou d’utiliser les outils d’administration Lync Server, vérifiez que vous avez examiné les exigences en matière d’infrastructure, de système d’exploitation, de logiciel et d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="78d96-109">Ensure that you review infrastructure, operating system, software, and administrator rights requirements before you install or use the Lync Server administrative tools.</span></span> <span data-ttu-id="78d96-110">Pour plus d’informations sur les exigences d’infrastructure, voir [administrative Tools infrastructure Requirements in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78d96-110">For details about infrastructure requirements, see [Administrative tools infrastructure requirements in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md).</span></span> <span data-ttu-id="78d96-111">Pour plus d’informations sur le système d’exploitation et la configuration logicielle requise pour l’installation des outils d’administration de Lync Server, voir [serveur et outils pris en charge par le système d’exploitation dans Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [autres logiciels requis pour Lync Server 2013](lync-server-2013-additional-software-requirements.md), ainsi que la [prise en charge et les exigences des serveurs supplémentaires dans Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78d96-111">For details about operating system and software requirements to install the Lync Server administrative tools, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md), and [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span></span> <span data-ttu-id="78d96-112">Les droits et autorisations de l’utilisateur nécessaires à l’installation et à l’utilisation des outils sont décrits dans la section [droits et autorisations d’administrateur requis pour la configuration et l’administration de Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).</span><span class="sxs-lookup"><span data-stu-id="78d96-112">The user rights and permissions required to install and use the tools are described in [Administrator rights and permissions required for setup and administration of Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).</span></span>

<span data-ttu-id="78d96-113">Les outils d’administration se composent des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="78d96-113">The administrative tools consist of the following:</span></span>

  - <span data-ttu-id="78d96-114">**L’Assistant**   déploiement Lync Server permet de déployer Lync Server et d’installer tous les outils d’administration.</span><span class="sxs-lookup"><span data-stu-id="78d96-114">**Lync Server Deployment Wizard**   Use to deploy Lync Server and to install all administrative tools.</span></span>

  - <span data-ttu-id="78d96-115">**Le générateur**   de topologies Lync Server permet de définir les composants de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="78d96-115">**Lync Server Topology Builder**   Use to define components in your deployment.</span></span>

  - <span data-ttu-id="78d96-116">**Le panneau de configuration**   Lync Server permet de gérer en continu votre déploiement à l’aide d’une interface Web.</span><span class="sxs-lookup"><span data-stu-id="78d96-116">**Lync Server Control Panel**   Use for ongoing management of your deployment by using a web-based interface.</span></span>

  - <span data-ttu-id="78d96-117">**Lync Server Management Shell**   utilisez pour la gestion continue de votre déploiement à l’aide de la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="78d96-117">**Lync Server Management Shell**   Use for ongoing management of your deployment by using the command line.</span></span>

  - <span data-ttu-id="78d96-118">**Outil de journalisation Lync Server**   utilisé pour résoudre les problèmes de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="78d96-118">**Lync Server Logging tool**   Use to troubleshoot problems in your deployment.</span></span>

  - <span data-ttu-id="78d96-119">**Le service**   de journalisation centralisée collecte les fichiers journaux et de suivi à partir d’un ordinateur, d’un pool, d’un site ou d’un global.</span><span class="sxs-lookup"><span data-stu-id="78d96-119">**Centralized Logging Service**   Collect logs and trace files from one computer, pool, site or global.</span></span> <span data-ttu-id="78d96-120">Sélectionnez et définissez des scénarios qui contiennent des fournisseurs, des indicateurs et des niveaux de suivi.</span><span class="sxs-lookup"><span data-stu-id="78d96-120">Select and define scenarios that contain providers, flags and trace levels.</span></span> <span data-ttu-id="78d96-121">La journalisation est collectée, agrégée et affichée avec des outils tels que n’importe quel outil basé sur du texte ou Snooper. exe.</span><span class="sxs-lookup"><span data-stu-id="78d96-121">Logging is collected, aggregated and displayed with tools such as any text-based tool or Snooper.exe.</span></span>

<span data-ttu-id="78d96-122">Vous pouvez gérer votre déploiement en utilisant principalement le générateur de topologie et le panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="78d96-122">You can manage your deployment by primarily using Topology Builder and Lync Server Control Panel.</span></span>

<div>

## <a name="deployment-wizard"></a><span data-ttu-id="78d96-123">Assistant Déploiement</span><span class="sxs-lookup"><span data-stu-id="78d96-123">Deployment Wizard</span></span>

<span data-ttu-id="78d96-124">Vous devez utiliser l’Assistant Déploiement Lync Server inclus sur le support d’installation pour installer tous les outils d’administration sur un ordinateur sur lequel vous n’avez pas encore installé Lync Server.</span><span class="sxs-lookup"><span data-stu-id="78d96-124">You must use the Lync Server Deployment Wizard included on the installation media to install all administrative tools onto a computer on which you have not already installed Lync Server.</span></span> <span data-ttu-id="78d96-125">Pendant le processus d’installation des outils d’administration, l’Assistant Déploiement de Lync Server est installé localement avec les autres outils de sorte que vous puissiez l’utiliser ultérieurement pour installer des fichiers pour des composants supplémentaires ou supprimer des fichiers pour les composants dont vous ne voulez pas sur le ci.</span><span class="sxs-lookup"><span data-stu-id="78d96-125">During the administrative tools installation process, the Lync Server Deployment Wizard is installed locally along with the other tools so that you can later use it to install files for additional components or remove files for components that you do not want on the computer.</span></span>

<span data-ttu-id="78d96-126">Pour plus d’informations sur l’exécution de l’Assistant Déploiement de Lync Server pour la première fois à partir du support d’installation de Lync Server, voir [install Lync server 2013 administrative Tools](lync-server-2013-install-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="78d96-126">For details about how to run the Lync Server Deployment Wizard for the first time from the Lync Server installation media, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span>

</div>

<div>

## <a name="topology-builder"></a><span data-ttu-id="78d96-127">Générateur de topologies</span><span class="sxs-lookup"><span data-stu-id="78d96-127">Topology Builder</span></span>

<span data-ttu-id="78d96-128">Pour plus d’informations sur les tâches de déploiement que vous pouvez effectuer à l’aide du générateur de topologie, reportez-vous à la documentation de déploiement pour chaque rôle serveur.</span><span class="sxs-lookup"><span data-stu-id="78d96-128">For details about deployment tasks that you can you perform by using Topology Builder, see the Deployment documentation for each server role.</span></span>

</div>

<div>

## <a name="lync-server-control-panel"></a><span data-ttu-id="78d96-129">Panneau de commande Lync Server</span><span class="sxs-lookup"><span data-stu-id="78d96-129">Lync Server Control Panel</span></span>

<span data-ttu-id="78d96-130">Vous pouvez utiliser le panneau de configuration Lync Server 2013 pour effectuer la plupart des tâches d’administration nécessaires à la gestion et à la maintenance de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="78d96-130">You can use Lync Server 2013 Control Panel to perform most of the administrative tasks required to manage and maintain Lync Server 2013.</span></span> <span data-ttu-id="78d96-131">Le panneau de configuration Lync Server vous fournit une interface utilisateur graphique (GUI) pour gérer la configuration des serveurs exécutant Lync Server, en plus des utilisateurs, des clients et des appareils de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="78d96-131">Lync Server Control Panel provides you with a graphical user interface (GUI) to manage the configuration of the servers running Lync Server, in addition to the users, clients, and devices in your organization.</span></span> <span data-ttu-id="78d96-132">Lync Server Management Shell utilise le panneau de configuration Lync Server comme mécanisme sous-jacent pour effectuer la configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="78d96-132">Lync Server Management Shell uses Lync Server Control Panel as the underlying mechanism to perform Lync Server configuration.</span></span>

<span data-ttu-id="78d96-133">Le panneau de configuration Lync Server est automatiquement installé sur chaque serveur frontal Lync Server ou serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="78d96-133">Lync Server Control Panel is automatically installed on every Lync Server Front End Server or Standard Edition server.</span></span> <span data-ttu-id="78d96-134">Dans cette version, l’administration des serveurs Edge s’effectue à distance.</span><span class="sxs-lookup"><span data-stu-id="78d96-134">In this release, you administer Edge Servers remotely.</span></span> <span data-ttu-id="78d96-135">Vous pouvez également installer le panneau de configuration Lync Server sur un autre ordinateur, tel qu’une console de gestion à partir de laquelle vous souhaitez centraliser la gestion de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="78d96-135">You can also install Lync Server Control Panel on another computer, such as a management console from which you want to centrally manage Lync Server.</span></span> <span data-ttu-id="78d96-136">Pour plus d’informations, reportez-vous à la rubrique [install Lync Server 2013 administrative Tools](lync-server-2013-install-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="78d96-136">For details, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="78d96-137">Pour configurer les paramètres à l’aide du panneau de configuration Lync Server, vous devez être connecté à l’aide d’un compte affecté au rôle CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="78d96-137">To configure settings using Lync Server Control Panel, you must be logged in using an account that is assigned to the CsAdministrator role.</span></span> <span data-ttu-id="78d96-138">Pour plus d’informations sur les rôles d’administration prédéfinis disponibles dans Lync Server 2013, reportez-vous à la rubrique <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="78d96-138">For details about the predefined administrative roles available in Lync Server 2013, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="78d96-139">Pour configurer les paramètres à l’aide du panneau de configuration Lync Server, vous devez également utiliser un ordinateur avec une résolution d’écran minimale de 1024 x 768.</span><span class="sxs-lookup"><span data-stu-id="78d96-139">To configure settings using Lync Server Control Panel, you must also use a computer with a minimum screen resolution of 1024 x 768.</span></span></P></LI></UL>



</div>

</div>

<div>

## <a name="lync-server-management-shell"></a><span data-ttu-id="78d96-140">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="78d96-140">Lync Server Management Shell</span></span>

<span data-ttu-id="78d96-141">Dans Lync Server, Lync Server Management Shell fournit une nouvelle méthode d’administration et de gestion.</span><span class="sxs-lookup"><span data-stu-id="78d96-141">In Lync Server, the Lync Server Management Shell provides a new method for administration and management.</span></span> <span data-ttu-id="78d96-142">Lync Server Management Shell est une interface de gestion puissante, basée sur l’interface de ligne de commande Windows PowerShell, qui inclut un ensemble complet d’applets de commande propres à Lync Server.</span><span class="sxs-lookup"><span data-stu-id="78d96-142">Lync Server Management Shell is a powerful management interface, built on the Windows PowerShell command-line interface, that includes a comprehensive set of cmdlets that are specific to Lync Server.</span></span> <span data-ttu-id="78d96-143">Avec Lync Server Management Shell, vous bénéficiez d’un ensemble complet de contrôles de configuration et d’automatisation.</span><span class="sxs-lookup"><span data-stu-id="78d96-143">With Lync Server Management Shell, you gain a rich set of configuration and automation controls.</span></span> <span data-ttu-id="78d96-144">Le générateur de topologie et le panneau de configuration Lync Server implémentent tous deux des sous-ensembles de ces applets de commande pour prendre en charge la gestion de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="78d96-144">Topology Builder and Lync Server Control Panel both implement subsets of these cmdlets to support management of Lync Server.</span></span> <span data-ttu-id="78d96-145">Lync Server Management Shell inclut des applets de commande pour toutes les tâches d’administration de Lync Server, et vous pouvez utiliser les applets de commande individuellement pour gérer votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="78d96-145">The Lync Server Management Shell includes cmdlets for all Lync Server administration tasks, and you can use the cmdlets individually to manage your deployment.</span></span> <span data-ttu-id="78d96-146">Pour plus d’informations, reportez-vous à la documentation de [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) ou à l’aide de ligne de commande pour chaque cmdlet.</span><span class="sxs-lookup"><span data-stu-id="78d96-146">For details, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation or the command-line help for each cmdlet.</span></span>

</div>

<div>

## <a name="logging-tool"></a><span data-ttu-id="78d96-147">Outil de journalisation</span><span class="sxs-lookup"><span data-stu-id="78d96-147">Logging Tool</span></span>

<span data-ttu-id="78d96-148">L’outil de journalisation Lync Server facilite la résolution des problèmes en capturant les informations de journalisation et de suivi du produit pendant que le produit est en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="78d96-148">The Lync Server Logging Tool facilitates troubleshooting by capturing logging and tracing information from the product while the product is running.</span></span> <span data-ttu-id="78d96-149">Vous pouvez utiliser l’outil pour exécuter des sessions de débogage sur n’importe quel rôle de serveur Lync Server.</span><span class="sxs-lookup"><span data-stu-id="78d96-149">You can use the tool to run debug sessions on any Lync Server server role.</span></span> <span data-ttu-id="78d96-150">Pour plus d’informations sur l’outil de journalisation, voir la documentation de l’outil de journalisation [http://go.microsoft.com/fwlink/p/?linkId=199265](http://go.microsoft.com/fwlink/p/?linkid=199265)Lync Server 2010 dans la bibliothèque TechNet à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="78d96-150">For details about the Logging Tool, see the Lync Server 2010 Logging Tool documentation on the TechNet Library at [http://go.microsoft.com/fwlink/p/?linkId=199265](http://go.microsoft.com/fwlink/p/?linkid=199265).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="78d96-151">Le service de journalisation centralisée est recommandé pour toutes les collections de journalisation sur l’outil de journalisation Lync Server dans toutes les circonstances.</span><span class="sxs-lookup"><span data-stu-id="78d96-151">The Centralized Logging Service is recommended for all logging collection over the Lync Server Logging Tool in all circumstances.</span></span> <span data-ttu-id="78d96-152">L’outil de journalisation Lync Server continue de fonctionner, mais il interfère ou s’affiche principalement si le service de journalisation centralisée est déjà en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="78d96-152">The Lync Server Logging Tool will still work, but it will interfere or be rendered mostly ineffective if the Centralized Logging Service is already running.</span></span> <span data-ttu-id="78d96-153">Vous devez utiliser uniquement le service de journalisation centralisée ou l’outil de journalisation Lync Server, mais jamais les deux à la fois.</span><span class="sxs-lookup"><span data-stu-id="78d96-153">You should use only the Centralized Logging Service or the Lync Server Logging Tool, but never both concurrently.</span></span> <span data-ttu-id="78d96-154">Pour plus d’informations sur le service de journalisation centralisée et la raison pour laquelle vous devez l’utiliser exclusivement, voir <A href="lync-server-2013-using-the-centralized-logging-service.md">utilisation du service de journalisation centralisée dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="78d96-154">For more information on the Centralized Logging Service and why you should use it exclusively, see <A href="lync-server-2013-using-the-centralized-logging-service.md">Using the Centralized Logging Service in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="78d96-155">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="78d96-155">In This Section</span></span>

  - [<span data-ttu-id="78d96-156">Configuration requise pour l’infrastructure des outils d’administration dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78d96-156">Administrative tools infrastructure requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-infrastructure-requirements.md)

  - [<span data-ttu-id="78d96-157">Serveur et outils pris en charge par le système d’exploitation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78d96-157">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)

  - [<span data-ttu-id="78d96-158">Configuration logicielle requise pour les outils d’administration dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78d96-158">Administrative tools software requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-software-requirements.md)

  - [<span data-ttu-id="78d96-159">Droits et autorisations d’administrateur requis pour la configuration et l’administration de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78d96-159">Administrator rights and permissions required for setup and administration of Lync Server 2013</span></span>](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)

  - [<span data-ttu-id="78d96-160">Conditions requises pour publier une topologie dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78d96-160">Requirements to publish a topology in Lync Server 2013</span></span>](lync-server-2013-requirements-to-publish-a-topology.md)

  - [<span data-ttu-id="78d96-161">Installer les outils d’administration Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78d96-161">Install Lync Server 2013 administrative tools</span></span>](lync-server-2013-install-lync-server-administrative-tools.md)

  - [<span data-ttu-id="78d96-162">Ouvrir les outils d’administration de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78d96-162">Open Lync Server 2013 administrative tools</span></span>](lync-server-2013-open-lync-server-administrative-tools.md)

  - [<span data-ttu-id="78d96-163">Dépannage du panneau de configuration Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78d96-163">Troubleshooting Lync Server 2013 Control Panel</span></span>](lync-server-2013-troubleshooting-lync-server-2013-control-panel.md)

  - [<span data-ttu-id="78d96-164">Utilisation du service de journalisation centralisée dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78d96-164">Using the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-using-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="78d96-165">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="78d96-165">See Also</span></span>


[<span data-ttu-id="78d96-166">Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="78d96-166">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

