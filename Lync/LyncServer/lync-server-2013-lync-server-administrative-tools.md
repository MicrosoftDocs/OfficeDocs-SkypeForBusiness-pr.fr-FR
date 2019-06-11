---
title: 'Lync Server 2013 : Outils d’administration de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server administrative tools
ms:assetid: 9b006f93-4f3d-461d-89b8-e80a34fdb3c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195756(v=OCS.15)
ms:contentKeyID: 48184972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6756aee8d7c65b179fb5c1c15ca008b3bd205778
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830929"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-administrative-tools"></a><span data-ttu-id="12291-102">Outils d’administration de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12291-102">Lync Server 2013 administrative tools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12291-103">_**Dernière modification de la rubrique:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="12291-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="12291-104">Cette rubrique décrit les outils d’administration de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12291-104">This topic describes the administrative tools for Lync Server 2013.</span></span>

<span data-ttu-id="12291-105">Les outils d’administration sont installés par défaut sur chaque serveur Lync Server.</span><span class="sxs-lookup"><span data-stu-id="12291-105">The administrative tools are installed by default on each Lync Server server.</span></span> <span data-ttu-id="12291-106">Par ailleurs, vous pouvez installer les outils d’administration sur d’autres ordinateurs, par exemple des consoles d’administration dédiées.</span><span class="sxs-lookup"><span data-stu-id="12291-106">Additionally, you can install the administrative tools on other computers, such as dedicated administrative consoles.</span></span> <span data-ttu-id="12291-107">Pour connaître les procédures d’installation des outils d’administration, voir [installer les outils d’administration de Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="12291-107">For procedures to install the administrative tools, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span> <span data-ttu-id="12291-108">Pour consulter les procédures permettant d’ouvrir les outils d’exécution des tâches de gestion, voir [ouvrir les outils d’administration de Lync Server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="12291-108">For procedures to open the tools to perform management tasks, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

<span data-ttu-id="12291-109">Vérifiez que vous passez en revue les exigences en matière d’infrastructure, de système d’exploitation, de logiciels et de droits d’administrateur avant d’installer ou d’utiliser les outils d’administration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="12291-109">Ensure that you review infrastructure, operating system, software, and administrator rights requirements before you install or use the Lync Server administrative tools.</span></span> <span data-ttu-id="12291-110">Pour plus d’informations sur la configuration requise en matière d’infrastructure, voir la [Configuration requise infrastructure des outils d’administration dans Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12291-110">For details about infrastructure requirements, see [Administrative tools infrastructure requirements in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md).</span></span> <span data-ttu-id="12291-111">Pour plus d’informations sur le système d’exploitation et la configuration logicielle requise pour l’installation des outils d’administration de Lync Server, reportez-vous à la rubrique [prise en charge des systèmes d’exploitation serveur et outils dans Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [configuration logicielle requise pour Lync Server 2013](lync-server-2013-additional-software-requirements.md)et [ La prise en charge et les exigences serveur supplémentaires dans Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12291-111">For details about operating system and software requirements to install the Lync Server administrative tools, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md), and [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span></span> <span data-ttu-id="12291-112">Les droits d’utilisateur et les autorisations nécessaires pour installer et utiliser les outils sont décrits dans [droits d’administrateur et autorisations nécessaires pour l’installation et l’administration de Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).</span><span class="sxs-lookup"><span data-stu-id="12291-112">The user rights and permissions required to install and use the tools are described in [Administrator rights and permissions required for setup and administration of Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).</span></span>

<span data-ttu-id="12291-113">Les outils d’administration sont les suivants:</span><span class="sxs-lookup"><span data-stu-id="12291-113">The administrative tools consist of the following:</span></span>

  - <span data-ttu-id="12291-114">**L’Assistant**   déploiement de Lync Server vous permet de déployer Lync Server et d’installer tous les outils d’administration.</span><span class="sxs-lookup"><span data-stu-id="12291-114">**Lync Server Deployment Wizard**   Use to deploy Lync Server and to install all administrative tools.</span></span>

  - <span data-ttu-id="12291-115">**Le générateur**   de topologie Lync Server permet de définir des composants dans votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="12291-115">**Lync Server Topology Builder**   Use to define components in your deployment.</span></span>

  - <span data-ttu-id="12291-116">**Panneau de configuration**   de Lync Server pour une gestion suivie de votre déploiement à l’aide d’une interface basée sur le Web.</span><span class="sxs-lookup"><span data-stu-id="12291-116">**Lync Server Control Panel**   Use for ongoing management of your deployment by using a web-based interface.</span></span>

  - <span data-ttu-id="12291-117">**Lync Server Management Shell**   vous permet d’utiliser la ligne de commande pour gérer en continu votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="12291-117">**Lync Server Management Shell**   Use for ongoing management of your deployment by using the command line.</span></span>

  - <span data-ttu-id="12291-118">**Outil de journalisation Lync Server**   à utiliser pour résoudre les problèmes de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="12291-118">**Lync Server Logging tool**   Use to troubleshoot problems in your deployment.</span></span>

  - <span data-ttu-id="12291-119">**Le service**   de connexion centralisé collecte les journaux et trace les fichiers à partir d’un ordinateur, d’une réserve, d’un site ou d’une connexion globale.</span><span class="sxs-lookup"><span data-stu-id="12291-119">**Centralized Logging Service**   Collect logs and trace files from one computer, pool, site or global.</span></span> <span data-ttu-id="12291-120">Sélectionner et définir des scénarios qui contiennent des fournisseurs, des indicateurs et des niveaux de suivi.</span><span class="sxs-lookup"><span data-stu-id="12291-120">Select and define scenarios that contain providers, flags and trace levels.</span></span> <span data-ttu-id="12291-121">La journalisation est collectée, agrégée et affichée à l’aide d’outils tels que des outils de texte ou de la fonction Snoop. exe.</span><span class="sxs-lookup"><span data-stu-id="12291-121">Logging is collected, aggregated and displayed with tools such as any text-based tool or Snooper.exe.</span></span>

<span data-ttu-id="12291-122">Vous pouvez gérer votre déploiement en utilisant essentiellement le générateur de topologie et le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="12291-122">You can manage your deployment by primarily using Topology Builder and Lync Server Control Panel.</span></span>

<div>

## <a name="deployment-wizard"></a><span data-ttu-id="12291-123">Assistant Déploiement</span><span class="sxs-lookup"><span data-stu-id="12291-123">Deployment Wizard</span></span>

<span data-ttu-id="12291-124">Vous devez utiliser l’Assistant Déploiement de Lync Server inclus sur le média d’installation pour installer tous les outils d’administration sur un ordinateur sur lequel vous n’avez pas encore installé Lync Server.</span><span class="sxs-lookup"><span data-stu-id="12291-124">You must use the Lync Server Deployment Wizard included on the installation media to install all administrative tools onto a computer on which you have not already installed Lync Server.</span></span> <span data-ttu-id="12291-125">Pendant le processus d’installation des outils d’administration, l’Assistant Déploiement de Lync Server est installé en local avec les autres outils de sorte que vous puissiez l’utiliser ultérieurement pour installer des fichiers pour les composants supplémentaires ou supprimer des fichiers pour les composants que vous ne souhaitez pas voir sur le ordinateur.</span><span class="sxs-lookup"><span data-stu-id="12291-125">During the administrative tools installation process, the Lync Server Deployment Wizard is installed locally along with the other tools so that you can later use it to install files for additional components or remove files for components that you do not want on the computer.</span></span>

<span data-ttu-id="12291-126">Pour plus d’informations sur l’exécution de l’Assistant Déploiement de Lync Server pour la première fois à partir du support d’installation de Lync Server, voir [installer les outils d’administration de Lync server 2013](lync-server-2013-install-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="12291-126">For details about how to run the Lync Server Deployment Wizard for the first time from the Lync Server installation media, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span>

</div>

<div>

## <a name="topology-builder"></a><span data-ttu-id="12291-127">Générateur de topologie</span><span class="sxs-lookup"><span data-stu-id="12291-127">Topology Builder</span></span>

<span data-ttu-id="12291-128">Pour plus d’informations sur les tâches de déploiement que vous pouvez effectuer à l’aide du générateur de topologie, consultez la documentation de déploiement pour chaque rôle de serveur.</span><span class="sxs-lookup"><span data-stu-id="12291-128">For details about deployment tasks that you can you perform by using Topology Builder, see the Deployment documentation for each server role.</span></span>

</div>

<div>

## <a name="lync-server-control-panel"></a><span data-ttu-id="12291-129">Panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="12291-129">Lync Server Control Panel</span></span>

<span data-ttu-id="12291-130">Vous pouvez utiliser le panneau de configuration de Lync Server 2013 pour effectuer la plupart des tâches administratives nécessaires à la gestion et à la gestion de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12291-130">You can use Lync Server 2013 Control Panel to perform most of the administrative tasks required to manage and maintain Lync Server 2013.</span></span> <span data-ttu-id="12291-131">Le panneau de configuration de Lync Server vous offre une interface utilisateur graphique (GUI) pour gérer la configuration des serveurs exécutant Lync Server, en plus des utilisateurs, des clients et des appareils de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="12291-131">Lync Server Control Panel provides you with a graphical user interface (GUI) to manage the configuration of the servers running Lync Server, in addition to the users, clients, and devices in your organization.</span></span> <span data-ttu-id="12291-132">Lync Server Management Shell utilise le panneau de configuration de Lync Server comme mécanisme sous-jacent pour effectuer la configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="12291-132">Lync Server Management Shell uses Lync Server Control Panel as the underlying mechanism to perform Lync Server configuration.</span></span>

<span data-ttu-id="12291-133">Le panneau de configuration de Lync Server est automatiquement installé sur tous les serveurs front end Server Lync Server ou Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="12291-133">Lync Server Control Panel is automatically installed on every Lync Server Front End Server or Standard Edition server.</span></span> <span data-ttu-id="12291-134">Dans cette version, vous administrez les serveurs Edge à distance.</span><span class="sxs-lookup"><span data-stu-id="12291-134">In this release, you administer Edge Servers remotely.</span></span> <span data-ttu-id="12291-135">Vous pouvez également installer le panneau de configuration de Lync Server sur un autre ordinateur, tel qu’une console de gestion à partir de laquelle vous voulez gérer de manière centralisée Lync Server.</span><span class="sxs-lookup"><span data-stu-id="12291-135">You can also install Lync Server Control Panel on another computer, such as a management console from which you want to centrally manage Lync Server.</span></span> <span data-ttu-id="12291-136">Pour en savoir plus, voir [installer les outils d’administration de Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="12291-136">For details, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="12291-137">Pour configurer les paramètres à l’aide du panneau de configuration de Lync Server, vous devez être connecté à l’aide d’un compte attribué au rôle CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="12291-137">To configure settings using Lync Server Control Panel, you must be logged in using an account that is assigned to the CsAdministrator role.</span></span> <span data-ttu-id="12291-138">Pour plus d’informations sur les rôles d’administration prédéfinis disponibles dans Lync Server 2013, voir <A href="lync-server-2013-planning-for-role-based-access-control.md">planification du contrôle d’accès basé sur les rôles dans Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="12291-138">For details about the predefined administrative roles available in Lync Server 2013, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="12291-139">Pour configurer les paramètres à l’aide du panneau de configuration de Lync Server, vous devez également utiliser un ordinateur avec une résolution d’écran minimum de 1024 x 768.</span><span class="sxs-lookup"><span data-stu-id="12291-139">To configure settings using Lync Server Control Panel, you must also use a computer with a minimum screen resolution of 1024 x 768.</span></span></P></LI></UL>



</div>

</div>

<div>

## <a name="lync-server-management-shell"></a><span data-ttu-id="12291-140">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="12291-140">Lync Server Management Shell</span></span>

<span data-ttu-id="12291-141">Dans Lync Server, Lync Server Management Shell fournit une nouvelle méthode d’administration et de gestion.</span><span class="sxs-lookup"><span data-stu-id="12291-141">In Lync Server, the Lync Server Management Shell provides a new method for administration and management.</span></span> <span data-ttu-id="12291-142">Lync Server Management Shell est une interface de gestion puissante, basée sur l’interface de ligne de commande Windows PowerShell, qui inclut un ensemble complet d’applets de commande spécifiques à Lync Server.</span><span class="sxs-lookup"><span data-stu-id="12291-142">Lync Server Management Shell is a powerful management interface, built on the Windows PowerShell command-line interface, that includes a comprehensive set of cmdlets that are specific to Lync Server.</span></span> <span data-ttu-id="12291-143">Lync Server Management Shell vous permet d’accéder à un large éventail de contrôles de configuration et d’automatisation.</span><span class="sxs-lookup"><span data-stu-id="12291-143">With Lync Server Management Shell, you gain a rich set of configuration and automation controls.</span></span> <span data-ttu-id="12291-144">Le générateur de topologie et le panneau de configuration de Lync Server implémentent les sous-ensembles de ces applets de commande pour la prise en charge de la gestion de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="12291-144">Topology Builder and Lync Server Control Panel both implement subsets of these cmdlets to support management of Lync Server.</span></span> <span data-ttu-id="12291-145">Lync Server Management Shell inclut des cmdlets pour toutes les tâches d’administration de Lync Server et vous pouvez utiliser les applets de cmdlet individuellement pour gérer votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="12291-145">The Lync Server Management Shell includes cmdlets for all Lync Server administration tasks, and you can use the cmdlets individually to manage your deployment.</span></span> <span data-ttu-id="12291-146">Pour plus d’informations, reportez-vous à la documentation de [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) ou à l’aide de la ligne de commande pour chaque cmdlet.</span><span class="sxs-lookup"><span data-stu-id="12291-146">For details, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation or the command-line help for each cmdlet.</span></span>

</div>

<div>

## <a name="logging-tool"></a><span data-ttu-id="12291-147">Outil d’enregistrement</span><span class="sxs-lookup"><span data-stu-id="12291-147">Logging Tool</span></span>

<span data-ttu-id="12291-148">L’outil de journalisation de Lync Server facilite la résolution des problèmes en capturant les informations de journalisation et de suivi à partir du produit lorsque le produit est en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="12291-148">The Lync Server Logging Tool facilitates troubleshooting by capturing logging and tracing information from the product while the product is running.</span></span> <span data-ttu-id="12291-149">Vous pouvez utiliser l’outil pour exécuter des sessions de débogage sur n’importe quel rôle serveur Lync Server.</span><span class="sxs-lookup"><span data-stu-id="12291-149">You can use the tool to run debug sessions on any Lync Server server role.</span></span> <span data-ttu-id="12291-150">Pour plus d’informations sur l’outil de journalisation, voir la documentation de l’outil de journalisation [http://go.microsoft.com/fwlink/p/?linkId=199265](http://go.microsoft.com/fwlink/p/?linkid=199265)Lync Server 2010 dans la bibliothèque TechNet à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="12291-150">For details about the Logging Tool, see the Lync Server 2010 Logging Tool documentation on the TechNet Library at [http://go.microsoft.com/fwlink/p/?linkId=199265](http://go.microsoft.com/fwlink/p/?linkid=199265).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="12291-151">Le service de journalisation centralisé est recommandé pour toutes les collections de journaux par le biais de l’outil de journalisation Lync Server en toutes circonstances.</span><span class="sxs-lookup"><span data-stu-id="12291-151">The Centralized Logging Service is recommended for all logging collection over the Lync Server Logging Tool in all circumstances.</span></span> <span data-ttu-id="12291-152">L’outil de journalisation de Lync Server fonctionne toujours, mais il interfère ou s’affiche de façon plus efficace si le service de journalisation centralisé est déjà en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="12291-152">The Lync Server Logging Tool will still work, but it will interfere or be rendered mostly ineffective if the Centralized Logging Service is already running.</span></span> <span data-ttu-id="12291-153">Vous devez uniquement utiliser le service de journalisation centralisé ou l’outil de journalisation de Lync Server, mais jamais les deux simultanément.</span><span class="sxs-lookup"><span data-stu-id="12291-153">You should use only the Centralized Logging Service or the Lync Server Logging Tool, but never both concurrently.</span></span> <span data-ttu-id="12291-154">Pour plus d’informations sur le service de journalisation centralisé et sur les raisons pour lesquelles vous devriez l’utiliser exclusivement, voir <A href="lync-server-2013-using-the-centralized-logging-service.md">utiliser le service de journalisation centralisé dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="12291-154">For more information on the Centralized Logging Service and why you should use it exclusively, see <A href="lync-server-2013-using-the-centralized-logging-service.md">Using the Centralized Logging Service in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="12291-155">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="12291-155">In This Section</span></span>

  - [<span data-ttu-id="12291-156">Exigences d’infrastructure des outils d’administration dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12291-156">Administrative tools infrastructure requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-infrastructure-requirements.md)

  - [<span data-ttu-id="12291-157">Prise en charge du système d’exploitation pour le serveur et les outils dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12291-157">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)

  - [<span data-ttu-id="12291-158">Configuration logicielle requise pour les outils d’administration dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12291-158">Administrative tools software requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-software-requirements.md)

  - [<span data-ttu-id="12291-159">Droits et autorisations d’administrateur requis pour la configuration et l’administration de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12291-159">Administrator rights and permissions required for setup and administration of Lync Server 2013</span></span>](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)

  - [<span data-ttu-id="12291-160">Conditions requises pour publier une topologie dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12291-160">Requirements to publish a topology in Lync Server 2013</span></span>](lync-server-2013-requirements-to-publish-a-topology.md)

  - [<span data-ttu-id="12291-161">Installation des outils d’administration Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12291-161">Install Lync Server 2013 administrative tools</span></span>](lync-server-2013-install-lync-server-administrative-tools.md)

  - [<span data-ttu-id="12291-162">Ouvrez les outils d’administration de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12291-162">Open Lync Server 2013 administrative tools</span></span>](lync-server-2013-open-lync-server-administrative-tools.md)

  - [<span data-ttu-id="12291-163">Résolution des problèmes liés à Lync Server 2013 Control Panel</span><span class="sxs-lookup"><span data-stu-id="12291-163">Troubleshooting Lync Server 2013 Control Panel</span></span>](lync-server-2013-troubleshooting-lync-server-2013-control-panel.md)

  - [<span data-ttu-id="12291-164">Utiliser le service de journalisation centralisé dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12291-164">Using the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-using-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="12291-165">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="12291-165">See Also</span></span>


[<span data-ttu-id="12291-166">Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="12291-166">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

