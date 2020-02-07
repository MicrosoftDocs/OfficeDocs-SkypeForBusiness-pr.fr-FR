---
title: Utilisation de la mémoire par Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: Comment Microsoft teams utilise la mémoire système et pourquoi l’utilisation de la mémoire est identique entre l’application de bureau et l’application Web.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 05cbd2f4b6691c873393a7ba711e03aadf70a2f2
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836984"
---
# <a name="how-microsoft-teams-uses-memory"></a><span data-ttu-id="3aeaa-103">Utilisation de la mémoire par Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3aeaa-103">How Microsoft Teams uses memory</span></span>

<span data-ttu-id="3aeaa-104">Certains utilisateurs de Microsoft teams ont des questions sur l’utilisation de la mémoire par Teams.</span><span class="sxs-lookup"><span data-stu-id="3aeaa-104">Some Microsoft Teams users have questions about how Teams uses memory.</span></span> <span data-ttu-id="3aeaa-105">Cet article décrit la façon dont la mémoire est utilisée par teams et pourquoi l’application de bureau Teams (application) et l’application Web teams n’empêchent pas d’autres applications et charges de travail sur le même ordinateur d’avoir suffisamment de mémoire pour fonctionner de manière optimale.</span><span class="sxs-lookup"><span data-stu-id="3aeaa-105">This article describes how memory is used by Teams, and why the Teams desktop application (app) and the Teams web app do not prevent other apps and workloads on the same computer from having enough memory to run optimally.</span></span> <span data-ttu-id="3aeaa-106">Teams est conçu pour utiliser la technologie Web moderne.</span><span class="sxs-lookup"><span data-stu-id="3aeaa-106">Teams is designed to use modern web technology.</span></span> <span data-ttu-id="3aeaa-107">Pour ce faire, le client de bureau teams a été développé sur Electron, qui utilise le chrome pour le rendu.</span><span class="sxs-lookup"><span data-stu-id="3aeaa-107">To achieve this, the Teams desktop client was developed on Electron, which uses Chromium for rendering.</span></span> <span data-ttu-id="3aeaa-108">Il s’agit du même moteur de rendu que sur la plupart des navigateurs les plus populaires du jour, y compris les périphériques Edge et chrome.</span><span class="sxs-lookup"><span data-stu-id="3aeaa-108">This is the same rendering engine behind many of today’s most popular browsers, including Edge and Chrome.</span></span>

## <a name="how-teams-works"></a><span data-ttu-id="3aeaa-109">Fonctionnement d’teams</span><span class="sxs-lookup"><span data-stu-id="3aeaa-109">How Teams works</span></span>

<span data-ttu-id="3aeaa-110">Les équipes spécialisées en matière d’électrons permettent un développement plus rapide et disposent également de la parité entre les versions d’équipe sur différents systèmes d’exploitation (Windows, Mac et Linux).</span><span class="sxs-lookup"><span data-stu-id="3aeaa-110">Teams being designed on Electron allows for faster development, and it also maintains parity between Teams versions across different operating systems (Windows, Mac, and Linux).</span></span> <span data-ttu-id="3aeaa-111">Cette parité est possible, car le son pour le son de type « Electron » et « chrome » entretiennent une base de code similaire pour toutes les versions</span><span class="sxs-lookup"><span data-stu-id="3aeaa-111">This parity is possible because Electron and Chromium maintain a similar code base across all versions.</span></span> <span data-ttu-id="3aeaa-112">Un autre avantage de cette architecture est le profil d’utilisation de mémoire similaire entre Team Web App et la version de bureau.</span><span class="sxs-lookup"><span data-stu-id="3aeaa-112">Another advantage of this architecture is there's a similar memory usage profile between the Teams web app and the desktop version.</span></span> <span data-ttu-id="3aeaa-113">L’application Web et les versions de bureau utilisent la mémoire de manière similaire à la façon dont un navigateur l’utiliserait.</span><span class="sxs-lookup"><span data-stu-id="3aeaa-113">Both the web app and the desktop versions use memory in a similar way to how a browser would use it.</span></span> <span data-ttu-id="3aeaa-114">Des informations supplémentaires sur l’électron sont disponibles sur [leur site Web](https://electronjs.org/).</span><span class="sxs-lookup"><span data-stu-id="3aeaa-114">More information about Electron is available at [their Web site](https://electronjs.org/).</span></span>

<span data-ttu-id="3aeaa-115">Pour plus d’informations, voir utilisation de la [mémoire de chrome](https://www.chromium.org/developers/memory-usage-backgrounder) et [concepts clés de la mémoire chrome](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md) .</span><span class="sxs-lookup"><span data-stu-id="3aeaa-115">See [Chromium Memory Usage](https://www.chromium.org/developers/memory-usage-backgrounder) and [Key Concepts in Chrome Memory](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md) for more information.</span></span>

<span data-ttu-id="3aeaa-116">L’image ci-dessous illustre l’utilisation de la mémoire côte à côte de l’application de bureau teams pour Windows et de l’application Web Teams (dans cet exemple, exécutée dans Google Chrome).</span><span class="sxs-lookup"><span data-stu-id="3aeaa-116">The following image shows side-by-side memory usages of the Teams desktop app for Windows and the Teams Web app (in this example, running in Google Chrome).</span></span>

![Application de bureau teams et utilisation de la mémoire Web App](media/teams-memory-clientweb.png)

## <a name="memory-usage-in-teams"></a><span data-ttu-id="3aeaa-118">Utilisation de la mémoire dans teams</span><span class="sxs-lookup"><span data-stu-id="3aeaa-118">Memory usage in Teams</span></span>

<span data-ttu-id="3aeaa-119">Il est important de comprendre le comportement *attendu* d’teams lorsqu’il s’agit de la mémoire système et de connaître les symptômes de véritables problèmes de mémoire système.</span><span class="sxs-lookup"><span data-stu-id="3aeaa-119">It is important to understand the *expected* behavior of Teams when it comes to system memory, and to know the symptoms of truly problematic system memory issues.</span></span>

### <a name="expected-memory-usage-by-teams"></a><span data-ttu-id="3aeaa-120">Utilisation de la mémoire prévue par teams</span><span class="sxs-lookup"><span data-stu-id="3aeaa-120">Expected memory usage by Teams</span></span>

<span data-ttu-id="3aeaa-121">Que vous utilisiez l’application de bureau teams ou Team Web App, chrome détecte la quantité de mémoire système disponible et utilise suffisamment de mémoire pour optimiser l’expérience de rendu.</span><span class="sxs-lookup"><span data-stu-id="3aeaa-121">Whether you're running the Teams desktop app or the Teams web app, Chromium detects how much system memory is available and utilizes enough of that memory to optimize the rendering experience.</span></span> <span data-ttu-id="3aeaa-122">Lorsque d’autres applications ou services nécessitent une mémoire système, le chrome libère de la mémoire pour ces processus.</span><span class="sxs-lookup"><span data-stu-id="3aeaa-122">When other apps or services require system memory, Chromium gives up memory to those processes.</span></span> <span data-ttu-id="3aeaa-123">Le chrome ajuste l’utilisation de la mémoire aux équipes de façon continue pour optimiser les performances des équipes sans avoir à influer sur tout autre élément en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="3aeaa-123">Chromium tunes Teams memory usage on an ongoing basis in order to optimize Teams performance without impacting anything else currently running.</span></span>

<span data-ttu-id="3aeaa-124">De cette façon, les charges de travail similaires peuvent utiliser des quantités variables de mémoire, en fonction de la quantité de mémoire système disponible.</span><span class="sxs-lookup"><span data-stu-id="3aeaa-124">In this way, similar Chromium workloads can utilize varying amounts of memory, depending on the amount of system memory that is available.</span></span>

<span data-ttu-id="3aeaa-125">Le graphique suivant illustre l’utilisation de la mémoire par teams sur quatre systèmes distincts, chacun avec des quantités différentes de mémoire disponibles.</span><span class="sxs-lookup"><span data-stu-id="3aeaa-125">The following graph depicts memory usage by Teams on four separate systems, each with different amounts of memory available.</span></span> <span data-ttu-id="3aeaa-126">Chacun des systèmes traite des charges de travail similaires (les mêmes applications sont ouvertes et exécutées).</span><span class="sxs-lookup"><span data-stu-id="3aeaa-126">Each of the systems is processing similar workloads (same apps open and running).</span></span>

![Utilisation de la mémoire par teams sur différents systèmes](media/teams-memory-usage.png)

<span data-ttu-id="3aeaa-128">Lorsque les ordinateurs disposent de plus de mémoire, teams utilise cette mémoire.</span><span class="sxs-lookup"><span data-stu-id="3aeaa-128">When computers have more memory, Teams will use that memory.</span></span> <span data-ttu-id="3aeaa-129">Dans les systèmes dont la mémoire est faible, teams utilisera moins.</span><span class="sxs-lookup"><span data-stu-id="3aeaa-129">In systems where memory is scarce, Teams will use less.</span></span> 

### <a name="symptoms-of-system-memory-issues"></a><span data-ttu-id="3aeaa-130">Symptômes liés aux problèmes de mémoire système</span><span class="sxs-lookup"><span data-stu-id="3aeaa-130">Symptoms of system memory issues</span></span>

<span data-ttu-id="3aeaa-131">Si vous voyez un ou plusieurs des problèmes suivants sur votre ordinateur, vous pouvez rencontrer des problèmes de mémoire système importants :</span><span class="sxs-lookup"><span data-stu-id="3aeaa-131">If you see one or more of the following symptoms on your computer, you could have a serious system memory issue:</span></span>

- <span data-ttu-id="3aeaa-132">Utilisation de la mémoire haute lorsque plusieurs applications de grande taille s’exécutent simultanément.</span><span class="sxs-lookup"><span data-stu-id="3aeaa-132">High memory use when multiple large applications are running simultaneously.</span></span>
- <span data-ttu-id="3aeaa-133">Baisse des performances du système ou applications suspendues.</span><span class="sxs-lookup"><span data-stu-id="3aeaa-133">Slow system performance or applications hanging.</span></span>
- <span data-ttu-id="3aeaa-134">Utilisation de la mémoire système globale de 90% ou une valeur supérieure dans toutes les applications.</span><span class="sxs-lookup"><span data-stu-id="3aeaa-134">Sustained overall system memory usage of 90% or higher across all apps.</span></span> <span data-ttu-id="3aeaa-135">En ce qui concerne l’utilisation de la mémoire, teams doit remettre en mémoire d’autres applications et charges de travail.</span><span class="sxs-lookup"><span data-stu-id="3aeaa-135">With this amount of memory usage, Teams should be giving memory back to other apps and workloads.</span></span> <span data-ttu-id="3aeaa-136">L’utilisation de la mémoire continue de 90% peut signifier que Teams ne donne pas de mémoire au système, ce qui indique un problème.</span><span class="sxs-lookup"><span data-stu-id="3aeaa-136">Sustained memory usage of 90% could mean Teams isn't giving memory back to the system, which indicates a problem.</span></span>

<span data-ttu-id="3aeaa-137">Les images suivantes montrent des exemples d’affichages dans le gestionnaire des tâches lorsque l’utilisation de la mémoire système est anormalement élevée.</span><span class="sxs-lookup"><span data-stu-id="3aeaa-137">The following images show examples of views in Task Manager when system memory usage is abnormally high.</span></span>

![Affichage utilisation de la mémoire dans teams du gestionnaire des tâches](media/teams-memory-high-mem-process-list.png)

![Graphique utilisation de la mémoire dans teams dans le gestionnaire des tâches](media/teams-memory-high-mem-process-list2.png)
