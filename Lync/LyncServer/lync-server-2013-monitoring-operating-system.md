---
title: 'Skype Entreprise Server 2015 : surveillance du système d’exploitation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring operating system
ms:assetid: 72406d3e-54c8-4796-8d6d-2144a5b6f030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720918(v=OCS.15)
ms:contentKeyID: 63969617
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2f8124afcf2d1acbde3518ff625d528d6e34a3e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826695"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-operating-system-in-lync-server-2013"></a><span data-ttu-id="5897f-102">Surveillance du système d’exploitation dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="5897f-102">Monitoring operating system in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5897f-103">_**Dernière modification de la rubrique:** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="5897f-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="5897f-104">Vous devez surveiller les performances de tous les serveurs et composants du serveur Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5897f-104">You must monitor the performance of all servers and components in the Lync Server 2013.</span></span> <span data-ttu-id="5897f-105">Évidemment, lֹ’un des composants les plus importants est le système d’exploitation proprement dit.</span><span class="sxs-lookup"><span data-stu-id="5897f-105">Obviously, one of the most important components is the operating system itself.</span></span> <span data-ttu-id="5897f-106">Lync Server 2013 prend en charge les éditions x64 de:</span><span class="sxs-lookup"><span data-stu-id="5897f-106">Lync Server 2013 supports x64 editions of:</span></span>

  - <span data-ttu-id="5897f-107">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="5897f-107">Windows Server 2008 R2</span></span>

  - <span data-ttu-id="5897f-108">Windows Server 2012 et Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="5897f-108">Windows Server 2012 and Windows Server 2012 R2</span></span>

<span data-ttu-id="5897f-109">Le moyen le plus transparent de surveiller un système d’exploitation consiste à utiliser le Pack de gestion du système d’exploitation Windows Server.</span><span class="sxs-lookup"><span data-stu-id="5897f-109">The most transparent way to monitor an operating system is by using Windows Server Operating System Management Pack.</span></span> <span data-ttu-id="5897f-110">Il fournit les principales notions fondamentales sur le contrôle, telles que les performances, l’État et la disponibilité des ordinateurs exécutant Windows Server 2012, Windows Server 2012 R2 et Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="5897f-110">It provides the fundamental monitoring basics, such as performance, health, and availability for computers that are running Windows Server 2012, Windows Server 2012 R2, and Windows Server 2008 R2.</span></span>

<span data-ttu-id="5897f-111">Si vous détectez, importez et répondez automatiquement aux événements importants et aux indicateurs de performance, ces modules de gestion réduisent les délais de résolution des problèmes et améliorent la disponibilité et les performances globales des systèmes exécutant Windows Server systèmes d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="5897f-111">By detecting, alerting, and automatically responding to important events and performance indicators, these management packs reduce resolution times for issues and increase the overall availability and performance of systems that are running the Windows Server operating systems.</span></span>

<span data-ttu-id="5897f-112">Outre les packs de gestion Windows Server appropriés pour System Center Operations Manager, les ressources et les outils système suivants peuvent être utilisés pour contrôler l’état du système d’exploitation (en fonction de la version du système d’exploitation).</span><span class="sxs-lookup"><span data-stu-id="5897f-112">Apart from relevant Windows Server management packs for System Center Operations Manager, the following system tools and resources can be used to monitor the health of the operating system (depending on the operating system version).</span></span>

<div>

## <a name="windows-server2008r2"></a><span data-ttu-id="5897f-113">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="5897f-113">Windows Server 2008 R2</span></span>

<span data-ttu-id="5897f-114">Windows Server 2008 R2 inclut les fonctionnalités et outils supplémentaires suivants pour permettre aux administrateurs d’effectuer le suivi et la gestion de base du système d’exploitation:</span><span class="sxs-lookup"><span data-stu-id="5897f-114">Windows Server 2008 R2 includes the following additional features and tools to help administrators with basic operating system monitoring and management:</span></span>

  - <span data-ttu-id="5897f-p103">L’**Analyseur de ressources Windows** est un outil puissant qui permet de comprendre comment les processus et les services utilisent les ressources système. Outre la surveillance de l’utilisation des ressources en temps réel, un analyseur des ressources peut aider à analyser les processus qui ne répondent pas, à identifier les applications qui utilisent des fichiers et à contrôler les processus et les services.</span><span class="sxs-lookup"><span data-stu-id="5897f-p103">**Windows Resource Monitor** is a powerful tool for understanding how system resources are used by processes and services. In addition to monitoring resource usage in real time, a Resource Monitor can help analyze unresponsive processes, identify which applications are using files, and control processes and services.</span></span>

  - <span data-ttu-id="5897f-p104">Le **Composant d’analyse de fiabilité** est un agent intégré qui fournit des informations détaillées sur l’utilisation du système et la fiabilité. Ces informations sont présentées dans l’interface de Windows Management Instrumentation (WMI) afin qu'elles puissent être réutilisées par les systèmes de lecture portables. En exposant le Composant d’analyse de fiabilité par le biais d’une interface WMI, les développeurs peuvent surveiller et analyser les applications, ce qui permet d’augmenter la fiabilité et les performances.</span><span class="sxs-lookup"><span data-stu-id="5897f-p104">**Reliability Analysis Component** is an in-box agent that provides detailed experience information on system usage and reliability. This information is exposed through a WMI interface to make it available for consumption by Portable Readers Systems. By exposing Reliability Analysis Component through a WMI interface, developers can monitor and analyze applications, increasing reliability and performance.</span></span>

  - <span data-ttu-id="5897f-120">**Windows Server 2008 R2** utilise le composant analyse de fiabilité intégré pour calculer un index de fiabilité qui fournit des informations sur l’utilisation globale du système et sa stabilité dans le temps.</span><span class="sxs-lookup"><span data-stu-id="5897f-120">**Windows Server 2008 R2** uses the built-in Reliability Analysis Component to calculate a reliability index, which provides information about overall system usage and stability over time.</span></span> <span data-ttu-id="5897f-121">The Reliability Analysis Component also keeps track of any important changes to the system that are likely to influence stability, such as Windows updates and application installations.</span><span class="sxs-lookup"><span data-stu-id="5897f-121">The Reliability Analysis Component also keeps track of any important changes to the system that are likely to influence stability, such as Windows updates and application installations.</span></span>

</div>

<div>

## <a name="windows-server2008-windows-reliability-and-performance-monitor"></a><span data-ttu-id="5897f-122">Moniteur de fiabilité et de performances Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="5897f-122">Windows Server 2008 Windows Reliability and Performance Monitor</span></span>

<span data-ttu-id="5897f-p106">L’Analyseur de fiabilité et de performances Windows est un composant logiciel enfichable de la console MMC (Microsoft Management Console), qui combine les fonctionnalités des outils autonomes précédents, dont Journaux et alertes de performance, Vérificateur des performances des serveurs et Moniteur système. Son interface graphique permet de personnaliser la collecte des données de performances et les sessions de trace d’événements.</span><span class="sxs-lookup"><span data-stu-id="5897f-p106">Windows Reliability and Performance Monitor is an MMC Snap-in that combines the functionality of previous stand-alone tools including Performance Logs and Alerts, Server Performance Advisor, and System Monitor. It provides a graphical interface for customizing performance data collection and Event Trace Sessions.</span></span>

<span data-ttu-id="5897f-125">Il inclut également le Moniteur de fiabilité, un composant logiciel enfichable de la console MMC (Microsoft Management Console), qui suit les modifications apportées au système, les compare aux variations de stabilité du système et fournit une représentation graphique de leur relation.</span><span class="sxs-lookup"><span data-stu-id="5897f-125">It also includes Reliability Monitor, an MMC Snap-in that tracks changes to the system and compares them to changes in system stability, and it provides a graphical view of their relationship.</span></span>

</div>

<div>

## <a name="windows-reliability-and-performance-monitor"></a><span data-ttu-id="5897f-126">Analyseur de fiabilité et de performances Windows</span><span class="sxs-lookup"><span data-stu-id="5897f-126">Windows Reliability and Performance Monitor</span></span>

<span data-ttu-id="5897f-127">Même si la fiabilité et le moniteur de performance Windows combinent des fonctionnalités d’anciens outils autonomes, tels que les journaux et alertes de performance, et le moniteur système et le conseiller en matière de performance du serveur, il fournit également une nouvelle fonctionnalité à Windows Server 2008 et Windows Server 2008 R2, comme suit:</span><span class="sxs-lookup"><span data-stu-id="5897f-127">While Windows Reliability and Performance Monitor combine functionalities of some former stand-alone tools such as Performance Logs and Alerts, and System Monitor and Server Performance Advisor, it also provides some new functionality to Windows Server 2008 and Windows Server 2008 R2, such as the following:</span></span>

  - <span data-ttu-id="5897f-128">Ensembles de collecteurs de données</span><span class="sxs-lookup"><span data-stu-id="5897f-128">Data Collector Sets</span></span>

  - <span data-ttu-id="5897f-129">Affichage des ressources</span><span class="sxs-lookup"><span data-stu-id="5897f-129">Resource View</span></span>

  - <span data-ttu-id="5897f-130">Analyseur de fiabilité</span><span class="sxs-lookup"><span data-stu-id="5897f-130">Reliability Monitor</span></span>

  - <span data-ttu-id="5897f-131">Assistants et modèles pour créer des journaux</span><span class="sxs-lookup"><span data-stu-id="5897f-131">Wizards and templates for creating logs</span></span>

<span data-ttu-id="5897f-p107">Un **ensemble de collecteurs de données** regroupe des collecteurs de données dans des éléments réutilisables à utiliser avec différents scénarios de performances. Une fois qu’un groupe de collecteurs de données est stocké dans un ensemble de collecteurs de données, des opérations, comme la planification, peuvent être appliquées à tout l’ensemble en modifiant simplement une propriété. L’Analyseur de fiabilité et de performances Windows inclut des modèles d’ensemble de collecteurs de données par défaut pour permettre aux administrateurs système de commencer immédiatement à collecter des données de performances spécifiques à un rôle ou à un scénario de surveillance.</span><span class="sxs-lookup"><span data-stu-id="5897f-p107">**Data Collector Set** groups data collectors into reusable elements for use with different performance monitoring scenarios. After a group of data collectors are stored as a Data Collector Set, operations such as scheduling can be applied to the whole set through a single property change.Windows Reliability and Performance Monitor includes default Data Collector Set templates to help system administrators begin immediately collecting performance data that is specific to a server role or monitoring scenario.</span></span>

<span data-ttu-id="5897f-p108">La page d’accueil de l’Analyseur de fiabilité et de performances Windows est le nouvel écran **Affichage des ressources**, qui offre une vue graphique en temps réel de l’utilisation du processeur, des disques, du réseau et de la mémoire. En développant chacun des éléments surveillés, les administrateurs système peuvent identifier les processus qui utilisent des ressources. Dans les versions antérieures de Windows, ces données en temps réel sur les processus étaient disponibles sous forme limitée dans le Gestionnaire de tâches.</span><span class="sxs-lookup"><span data-stu-id="5897f-p108">The home page of Windows Reliability and Performance Monitor is the new **Resource View** screen, which provides a real-time graphical overview of CPU, disk, network, and memory usage. By expanding each of these monitored elements, system administrators can identify which processes are using which resources. In earlier versions of Windows, this real-time, process-specific data was available only in limited form in Task Manager.</span></span>

<span data-ttu-id="5897f-p109">L’**Analyseur de fiabilité** calcule un indice de stabilité du système qui reflète les problèmes inattendus ayant eu une incidence négative sur la fiabilité. Une courbe de l’indice de stabilité dans le temps identifie rapidement les dates auxquelles les problèmes ont commencé à se produire. Le rapport de stabilité du système associé contient des détails permettant de corriger la cause de la perte de fiabilité. En affichant les modifications apportées au système (installation ou suppression d’applications, mises à jour du système d’exploitation, ajout ou modification de pilotes) en regard des échecs (échecs des applications, blocage du système d’exploitation, défaillances matérielles), il est possible de développer rapidement une stratégie pour résoudre ces problèmes.</span><span class="sxs-lookup"><span data-stu-id="5897f-p109">**Reliability Monitor** calculates a System Stability Index that reflects whether unexpected issues reduced the reliability of the system. A graph of the Stability Index over time quickly identifies dates when issues began to occur. The accompanying System Stability Report provides details to help troubleshoot the cause of reduced reliability. By viewing changes to the system (installation or removal of applications, updates to the operating system, or addition or modification of drivers) side by side with failures (application failures, operating system crashes, or hardware failures), a strategy for addressing the issues can be developed quickly.</span></span>

<span data-ttu-id="5897f-p110">Il est désormais possible d’ajouter des compteurs dans les fichiers journaux et de planifier leur début, leur fin et leur durée par le biais d’une **interface de type Assistant**. De plus, l’enregistrement de cette configuration sous forme de modèle permet aux administrateurs système de collecter le même journal sur les autres ordinateurs sans avoir à sélectionner de nouveau les collecteurs de données ou à planifier les processus. Les fonctionnalités de Journaux et alertes de performance ont été intégrées à l’Analyseur de fiabilité et de performances Windows pour une utilisation avec les ensembles de collecteurs de données.</span><span class="sxs-lookup"><span data-stu-id="5897f-p110">Adding counters to log files and scheduling their start, stop, and duration can now be performed through a **Wizard interface**. In addition, saving this configuration as a template enables system administrators to collect the same log on other computers without repeating the data collector selection and scheduling processes. Performance Logs and Alerts features were incorporated into the Windows Reliability and Performance Monitor for use with any Data Collector Set.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

