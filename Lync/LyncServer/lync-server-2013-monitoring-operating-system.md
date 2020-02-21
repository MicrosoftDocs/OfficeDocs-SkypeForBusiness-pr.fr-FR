---
title: 'Lync Server 2013 : surveillance du système d’exploitation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring operating system
ms:assetid: 72406d3e-54c8-4796-8d6d-2144a5b6f030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720918(v=OCS.15)
ms:contentKeyID: 63969617
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3857ffa37ac3b50be6dc35ed281616aafff87c48
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184697"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-operating-system-in-lync-server-2013"></a><span data-ttu-id="9b6b5-102">Surveillance du système d’exploitation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b6b5-102">Monitoring operating system in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b6b5-103">_**Dernière modification de la rubrique :** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="9b6b5-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="9b6b5-104">Vous devez surveiller les performances de tous les serveurs et composants dans le Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-104">You must monitor the performance of all servers and components in the Lync Server 2013.</span></span> <span data-ttu-id="9b6b5-105">Évidemment, l’un des composants les plus importants est le système d’exploitation lui-même.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-105">Obviously, one of the most important components is the operating system itself.</span></span> <span data-ttu-id="9b6b5-106">Lync Server 2013 prend en charge les éditions x64 de :</span><span class="sxs-lookup"><span data-stu-id="9b6b5-106">Lync Server 2013 supports x64 editions of:</span></span>

  - <span data-ttu-id="9b6b5-107">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="9b6b5-107">Windows Server 2008 R2</span></span>

  - <span data-ttu-id="9b6b5-108">Windows Server 2012 et Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="9b6b5-108">Windows Server 2012 and Windows Server 2012 R2</span></span>

<span data-ttu-id="9b6b5-109">Le moyen le plus transparent de surveiller un système d’exploitation consiste à utiliser le pack d’administration du système d’exploitation Windows Server.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-109">The most transparent way to monitor an operating system is by using Windows Server Operating System Management Pack.</span></span> <span data-ttu-id="9b6b5-110">Elle offre des notions de base de surveillance fondamentales, telles que les performances, l’intégrité et la disponibilité des ordinateurs qui exécutent Windows Server 2012, Windows Server 2012 R2 et Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-110">It provides the fundamental monitoring basics, such as performance, health, and availability for computers that are running Windows Server 2012, Windows Server 2012 R2, and Windows Server 2008 R2.</span></span>

<span data-ttu-id="9b6b5-111">En détectant, en alertant et en répondant automatiquement aux événements importants et aux indicateurs de performances, ces packs d’administration réduisent les temps de résolution des problèmes et augmentent la disponibilité et les performances globales des systèmes qui exécutent Windows Server systèmes d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-111">By detecting, alerting, and automatically responding to important events and performance indicators, these management packs reduce resolution times for issues and increase the overall availability and performance of systems that are running the Windows Server operating systems.</span></span>

<span data-ttu-id="9b6b5-112">Outre les packs de gestion Windows Server appropriés pour System Center Operations Manager, les ressources et outils système suivants peuvent être utilisés pour surveiller l’état du système d’exploitation (en fonction de la version du système d’exploitation).</span><span class="sxs-lookup"><span data-stu-id="9b6b5-112">Apart from relevant Windows Server management packs for System Center Operations Manager, the following system tools and resources can be used to monitor the health of the operating system (depending on the operating system version).</span></span>

<div>

## <a name="windows-server2008r2"></a><span data-ttu-id="9b6b5-113">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="9b6b5-113">Windows Server 2008 R2</span></span>

<span data-ttu-id="9b6b5-114">Windows Server 2008 R2 inclut les fonctionnalités et outils supplémentaires suivants pour aider les administrateurs à utiliser la surveillance et la gestion des systèmes d’exploitation de base :</span><span class="sxs-lookup"><span data-stu-id="9b6b5-114">Windows Server 2008 R2 includes the following additional features and tools to help administrators with basic operating system monitoring and management:</span></span>

  - <span data-ttu-id="9b6b5-115">Le **moniteur de ressource Windows** est un outil puissant pour comprendre comment les ressources système sont utilisées par les processus et les services.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-115">**Windows Resource Monitor** is a powerful tool for understanding how system resources are used by processes and services.</span></span> <span data-ttu-id="9b6b5-116">En plus de surveiller l’utilisation des ressources en temps réel, un moniteur de ressources peut vous aider à analyser les processus qui ne répondent pas, à identifier les applications qui utilisent des fichiers et à contrôler les processus et les services.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-116">In addition to monitoring resource usage in real time, a Resource Monitor can help analyze unresponsive processes, identify which applications are using files, and control processes and services.</span></span>

  - <span data-ttu-id="9b6b5-117">Le **composant d’analyse de la fiabilité** est un agent intégré qui fournit des informations détaillées sur l’utilisation et la fiabilité du système.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-117">**Reliability Analysis Component** is an in-box agent that provides detailed experience information on system usage and reliability.</span></span> <span data-ttu-id="9b6b5-118">Ces informations sont exposées via une interface WMI afin de la mettre à la disposition des systèmes de lecteurs d’ordinateurs portables.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-118">This information is exposed through a WMI interface to make it available for consumption by Portable Readers Systems.</span></span> <span data-ttu-id="9b6b5-119">En exposant le composant d’analyse de fiabilité via une interface WMI, les développeurs peuvent surveiller et analyser les applications, ce qui augmente la fiabilité et les performances.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-119">By exposing Reliability Analysis Component through a WMI interface, developers can monitor and analyze applications, increasing reliability and performance.</span></span>

  - <span data-ttu-id="9b6b5-120">**Windows Server 2008 R2** utilise le composant d’analyse de fiabilité intégré pour calculer un index de fiabilité, qui fournit des informations sur l’utilisation et la stabilité du système dans le temps.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-120">**Windows Server 2008 R2** uses the built-in Reliability Analysis Component to calculate a reliability index, which provides information about overall system usage and stability over time.</span></span> <span data-ttu-id="9b6b5-121">Le composant d’analyse de fiabilité effectue également le suivi des modifications importantes apportées au système susceptibles d’influencer la stabilité, telles que les mises à jour Windows et les installations d’applications.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-121">The Reliability Analysis Component also keeps track of any important changes to the system that are likely to influence stability, such as Windows updates and application installations.</span></span>

</div>

<div>

## <a name="windows-server2008-windows-reliability-and-performance-monitor"></a><span data-ttu-id="9b6b5-122">Moniteur de fiabilité et de performances Windows Server 2008 Windows</span><span class="sxs-lookup"><span data-stu-id="9b6b5-122">Windows Server 2008 Windows Reliability and Performance Monitor</span></span>

<span data-ttu-id="9b6b5-123">L’analyseur de fiabilité et de performances Windows est un composant logiciel enfichable MMC qui combine les fonctionnalités des outils autonomes précédents, y compris les journaux et alertes de performance, le conseiller serveur de performance et le moniteur système.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-123">Windows Reliability and Performance Monitor is an MMC Snap-in that combines the functionality of previous stand-alone tools including Performance Logs and Alerts, Server Performance Advisor, and System Monitor.</span></span> <span data-ttu-id="9b6b5-124">Il fournit une interface graphique pour la personnalisation des sessions de collecte de données de performances et de suivi d’événements.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-124">It provides a graphical interface for customizing performance data collection and Event Trace Sessions.</span></span>

<span data-ttu-id="9b6b5-125">Il inclut également le moniteur de fiabilité, un composant logiciel enfichable MMC qui effectue le suivi des modifications apportées au système et les compare aux modifications apportées à la stabilité du système, et fournit une vue graphique de leur relation.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-125">It also includes Reliability Monitor, an MMC Snap-in that tracks changes to the system and compares them to changes in system stability, and it provides a graphical view of their relationship.</span></span>

</div>

<div>

## <a name="windows-reliability-and-performance-monitor"></a><span data-ttu-id="9b6b5-126">Moniteur de fiabilité et de performances Windows</span><span class="sxs-lookup"><span data-stu-id="9b6b5-126">Windows Reliability and Performance Monitor</span></span>

<span data-ttu-id="9b6b5-127">Bien que le moniteur de fiabilité et de performances de Windows combine les fonctionnalités de certains anciens outils autonomes, tels que les journaux et alertes de performance, ainsi que le moniteur système et le conseiller de performance de serveur, il fournit également de nouvelles fonctionnalités à Windows Server 2008 et Windows Server 2008 R2, comme suit :</span><span class="sxs-lookup"><span data-stu-id="9b6b5-127">While Windows Reliability and Performance Monitor combine functionalities of some former stand-alone tools such as Performance Logs and Alerts, and System Monitor and Server Performance Advisor, it also provides some new functionality to Windows Server 2008 and Windows Server 2008 R2, such as the following:</span></span>

  - <span data-ttu-id="9b6b5-128">Ensembles de collecteurs de données</span><span class="sxs-lookup"><span data-stu-id="9b6b5-128">Data Collector Sets</span></span>

  - <span data-ttu-id="9b6b5-129">Affichage des ressources</span><span class="sxs-lookup"><span data-stu-id="9b6b5-129">Resource View</span></span>

  - <span data-ttu-id="9b6b5-130">Moniteur de fiabilité</span><span class="sxs-lookup"><span data-stu-id="9b6b5-130">Reliability Monitor</span></span>

  - <span data-ttu-id="9b6b5-131">Assistants et modèles pour la création de journaux</span><span class="sxs-lookup"><span data-stu-id="9b6b5-131">Wizards and templates for creating logs</span></span>

<span data-ttu-id="9b6b5-132">**Ensemble de collecteur de données** regroupe les collecteurs de données en éléments réutilisables pour une utilisation avec différents scénarios d’analyse des performances.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-132">**Data Collector Set** groups data collectors into reusable elements for use with different performance monitoring scenarios.</span></span> <span data-ttu-id="9b6b5-133">Une fois qu’un groupe de collecteurs de données est stocké en tant qu’ensemble de collecteur de données, des opérations telles que la planification peuvent être appliquées à l’ensemble du jeu par le biais d’une modification de propriété unique. L’analyseur de fiabilité et de performances de Windows inclut des modèles d’ensembles de collecteurs de données par défaut pour aider les administrateurs système à commencer immédiatement à collecter des données de performances propres à un rôle de serveur ou à un scénario de surveillance.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-133">After a group of data collectors are stored as a Data Collector Set, operations such as scheduling can be applied to the whole set through a single property change.Windows Reliability and Performance Monitor includes default Data Collector Set templates to help system administrators begin immediately collecting performance data that is specific to a server role or monitoring scenario.</span></span>

<span data-ttu-id="9b6b5-134">La page d’accueil de l’analyseur de fiabilité et de performances Windows est le nouvel écran de **vue des ressources** , qui fournit une représentation graphique en temps réel de l’utilisation de l’UC, du disque, du réseau et de la mémoire.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-134">The home page of Windows Reliability and Performance Monitor is the new **Resource View** screen, which provides a real-time graphical overview of CPU, disk, network, and memory usage.</span></span> <span data-ttu-id="9b6b5-135">En développant chacun de ces éléments surveillés, les administrateurs système peuvent identifier les processus qui utilisent les ressources.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-135">By expanding each of these monitored elements, system administrators can identify which processes are using which resources.</span></span> <span data-ttu-id="9b6b5-136">Dans les versions antérieures de Windows, ces données en temps réel, propres aux processus, étaient disponibles uniquement sous forme limitée dans le gestionnaire des tâches.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-136">In earlier versions of Windows, this real-time, process-specific data was available only in limited form in Task Manager.</span></span>

<span data-ttu-id="9b6b5-137">Le **moniteur de fiabilité** calcule un index de stabilité du système reflétant si des problèmes inattendus ont permis de réduire la fiabilité du système.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-137">**Reliability Monitor** calculates a System Stability Index that reflects whether unexpected issues reduced the reliability of the system.</span></span> <span data-ttu-id="9b6b5-138">Un graphique de l’index de stabilité au fil du temps identifie rapidement des dates lorsque des problèmes ont commencé.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-138">A graph of the Stability Index over time quickly identifies dates when issues began to occur.</span></span> <span data-ttu-id="9b6b5-139">Le rapport de stabilité du système associé fournit des informations pour vous aider à résoudre la cause d’une fiabilité réduite.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-139">The accompanying System Stability Report provides details to help troubleshoot the cause of reduced reliability.</span></span> <span data-ttu-id="9b6b5-140">En affichant les modifications apportées au système (installation ou suppression des applications, mises à jour du système d’exploitation ou ajout ou modification de pilotes) côte à côte avec des échecs (échecs d’applications, pannes du système d’exploitation ou défaillances matérielles), une stratégie pour la résolution des problèmes peut être développée rapidement.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-140">By viewing changes to the system (installation or removal of applications, updates to the operating system, or addition or modification of drivers) side by side with failures (application failures, operating system crashes, or hardware failures), a strategy for addressing the issues can be developed quickly.</span></span>

<span data-ttu-id="9b6b5-141">L’ajout de compteurs aux fichiers journaux et la planification de leur démarrage, de leur arrêt et de leur durée peuvent désormais être effectués via une **interface d’Assistant**.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-141">Adding counters to log files and scheduling their start, stop, and duration can now be performed through a **Wizard interface**.</span></span> <span data-ttu-id="9b6b5-142">De plus, l’enregistrement de cette configuration sous forme de modèle permet aux administrateurs système de collecter le même journal sur d’autres ordinateurs sans répéter la sélection du collecteur de données et les processus de planification.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-142">In addition, saving this configuration as a template enables system administrators to collect the same log on other computers without repeating the data collector selection and scheduling processes.</span></span> <span data-ttu-id="9b6b5-143">Les fonctionnalités journaux et alertes de performance ont été intégrées à l’analyseur de fiabilité et de performances de Windows pour être utilisées avec n’importe quel ensemble de collecteurs de données.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-143">Performance Logs and Alerts features were incorporated into the Windows Reliability and Performance Monitor for use with any Data Collector Set.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

