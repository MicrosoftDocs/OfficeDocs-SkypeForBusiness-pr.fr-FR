---
title: Utilisation de la mémoire par Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: En savoir plus sur l’utilisation de la mémoire système dans Microsoft Teams et les raisons pour lesquelles l’utilisation de mémoire est la même entre l’application de bureau et l’application web.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: d218c71a0e3ecdde40559d67e1ad3a408d65a5d9
ms.sourcegitcommit: 43dc627e9fef31a2508f54acf741000551ff68b5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2020
ms.locfileid: "48878718"
---
# <a name="how-microsoft-teams-uses-memory"></a><span data-ttu-id="639d9-103">Utilisation de la mémoire par Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="639d9-103">How Microsoft Teams uses memory</span></span>

<span data-ttu-id="639d9-104">Certains utilisateurs de Microsoft Teams ont des questions sur la façon dont Teams utilise la mémoire.</span><span class="sxs-lookup"><span data-stu-id="639d9-104">Some Microsoft Teams users have questions about how Teams uses memory.</span></span> <span data-ttu-id="639d9-105">Cet article décrit comment la mémoire est utilisée par Teams et pourquoi l’application de bureau Teams (application) et l’application web Teams n’empêchent pas les autres applications et charges de travail sur le même ordinateur d’avoir suffisamment de mémoire pour fonctionner de manière optimale.</span><span class="sxs-lookup"><span data-stu-id="639d9-105">This article describes how memory is used by Teams, and why the Teams desktop application (app) and the Teams web app do not prevent other apps and workloads on the same computer from having enough memory to run optimally.</span></span> <span data-ttu-id="639d9-106">Teams est conçu pour utiliser la technologie web moderne.</span><span class="sxs-lookup"><span data-stu-id="639d9-106">Teams is designed to use modern web technology.</span></span> <span data-ttu-id="639d9-107">Pour ce faire, le client de bureau Teams a été développé sur Electron, qui utilise Chromium pour le rendu.</span><span class="sxs-lookup"><span data-stu-id="639d9-107">To achieve this, the Teams desktop client was developed on Electron, which uses Chromium for rendering.</span></span> <span data-ttu-id="639d9-108">Il s’agit du même moteur de rendu derrière la plupart des navigateurs les plus populaires à ce jour, notamment Microsoft Edge et Chrome.</span><span class="sxs-lookup"><span data-stu-id="639d9-108">This is the same rendering engine behind many of today's most popular browsers, including Edge and Chrome.</span></span>

## <a name="how-teams-works"></a><span data-ttu-id="639d9-109">Fonctionnement de Teams</span><span class="sxs-lookup"><span data-stu-id="639d9-109">How Teams works</span></span>

<span data-ttu-id="639d9-110">La conception de Teams sur Electron permet un développement plus rapide, ainsi que la parité entre les versions de Teams sur différents systèmes d’exploitation (Windows, Mac et Linux).</span><span class="sxs-lookup"><span data-stu-id="639d9-110">Teams being designed on Electron allows for faster development, and it also maintains parity between Teams versions across different operating systems (Windows, Mac, and Linux).</span></span> <span data-ttu-id="639d9-111">Cette parité est possible, car Electron et Chromium conservent une base de code similaire dans toutes les versions.</span><span class="sxs-lookup"><span data-stu-id="639d9-111">This parity is possible because Electron and Chromium maintain a similar code base across all versions.</span></span> <span data-ttu-id="639d9-112">Un autre avantage de cette architecture est qu’il existe un profil d’utilisation de mémoire similaire entre l’application web Teams et la version de bureau.</span><span class="sxs-lookup"><span data-stu-id="639d9-112">Another advantage of this architecture is there's a similar memory usage profile between the Teams web app and the desktop version.</span></span> <span data-ttu-id="639d9-113">L’application web et les versions de bureau utilisent la mémoire de la même façon qu’un navigateur l’utiliserait.</span><span class="sxs-lookup"><span data-stu-id="639d9-113">Both the web app and the desktop versions use memory in a similar way to how a browser would use it.</span></span> <span data-ttu-id="639d9-114">Des informations supplémentaires sur Electron sont disponibles sur [leur site web.](https://electronjs.org/)</span><span class="sxs-lookup"><span data-stu-id="639d9-114">More information about Electron is available at [their Web site](https://electronjs.org/).</span></span>

<span data-ttu-id="639d9-115">Pour plus [d’informations, voir Utilisation de la mémoire Chromium](https://www.chromium.org/developers/memory-usage-backgrounder) et Concepts clés [dans la mémoire Chrome.](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md)</span><span class="sxs-lookup"><span data-stu-id="639d9-115">See [Chromium Memory Usage](https://www.chromium.org/developers/memory-usage-backgrounder) and [Key Concepts in Chrome Memory](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md) for more information.</span></span>

<span data-ttu-id="639d9-116">L’image suivante illustre les utilisations de la mémoire côte à côte de l’application de bureau Teams pour Windows et de l’application Web Teams (dans cet exemple, qui s’exécute dans Google Chrome).</span><span class="sxs-lookup"><span data-stu-id="639d9-116">The following image shows side-by-side memory usages of the Teams desktop app for Windows and the Teams Web app (in this example, running in Google Chrome).</span></span>

![Utilisation de la mémoire Teams pour l’application de bureau et l’application Web](media/teams-memory-clientweb.png)

## <a name="memory-usage-in-teams"></a><span data-ttu-id="639d9-118">Utilisation de la mémoire dans Teams</span><span class="sxs-lookup"><span data-stu-id="639d9-118">Memory usage in Teams</span></span>

<span data-ttu-id="639d9-119">Il est important  de comprendre le comportement attendu de Teams en ce qui concerne la mémoire système et de connaître les symptômes des problèmes de mémoire système véritablement problématiques.</span><span class="sxs-lookup"><span data-stu-id="639d9-119">It is important to understand the *expected* behavior of Teams when it comes to system memory, and to know the symptoms of truly problematic system memory issues.</span></span>

### <a name="expected-memory-usage-by-teams"></a><span data-ttu-id="639d9-120">Utilisation attendue de la mémoire par Teams</span><span class="sxs-lookup"><span data-stu-id="639d9-120">Expected memory usage by Teams</span></span>

<span data-ttu-id="639d9-121">Que vous exécutez l’application de bureau Teams ou l’application web Teams, Chromium détecte la quantité de mémoire système disponible et utilise suffisamment cette mémoire pour optimiser l’expérience de rendu.</span><span class="sxs-lookup"><span data-stu-id="639d9-121">Whether you're running the Teams desktop app or the Teams web app, Chromium detects how much system memory is available and utilizes enough of that memory to optimize the rendering experience.</span></span> <span data-ttu-id="639d9-122">Lorsque d’autres applications ou services nécessitent de la mémoire système, Chromium en fait la mémoire pour ces processus.</span><span class="sxs-lookup"><span data-stu-id="639d9-122">When other apps or services require system memory, Chromium gives up memory to those processes.</span></span> <span data-ttu-id="639d9-123">Chromium tunes Teams memory usage on angoing basis in order to optimize Teams performance without impacting anything else running.</span><span class="sxs-lookup"><span data-stu-id="639d9-123">Chromium tunes Teams memory usage on an ongoing basis in order to optimize Teams performance without impacting anything else currently running.</span></span>

<span data-ttu-id="639d9-124">Ainsi, les charges de travail Chromium similaires peuvent utiliser diverses quantités de mémoire, selon la quantité de mémoire système disponible.</span><span class="sxs-lookup"><span data-stu-id="639d9-124">In this way, similar Chromium workloads can utilize varying amounts of memory, depending on the amount of system memory that is available.</span></span>

<span data-ttu-id="639d9-125">Le graphique suivant illustre l’utilisation de la mémoire par Teams sur quatre systèmes distincts, chacun avec une quantité différente de mémoire disponible.</span><span class="sxs-lookup"><span data-stu-id="639d9-125">The following graph depicts memory usage by Teams on four separate systems, each with different amounts of memory available.</span></span> <span data-ttu-id="639d9-126">Chacun des systèmes traite des charges de travail similaires (les mêmes applications sont ouvertes et en cours d’exécution).</span><span class="sxs-lookup"><span data-stu-id="639d9-126">Each of the systems is processing similar workloads (same apps open and running).</span></span>

![Utilisation de la mémoire Teams dans différents systèmes](media/teams-memory-usage.png)

<span data-ttu-id="639d9-128">Lorsque les ordinateurs ont plus de mémoire, Teams utilise cette mémoire.</span><span class="sxs-lookup"><span data-stu-id="639d9-128">When computers have more memory, Teams will use that memory.</span></span> <span data-ttu-id="639d9-129">Dans les systèmes où la mémoire est en place, Teams en utilise moins.</span><span class="sxs-lookup"><span data-stu-id="639d9-129">In systems where memory is scarce, Teams will use less.</span></span>

### <a name="symptoms-of-system-memory-issues"></a><span data-ttu-id="639d9-130">Symptômes de problèmes de mémoire système</span><span class="sxs-lookup"><span data-stu-id="639d9-130">Symptoms of system memory issues</span></span>

<span data-ttu-id="639d9-131">Si vous constatez un ou plusieurs des symptômes suivants sur votre ordinateur, vous pouvez avoir un problème sérieux de mémoire système :</span><span class="sxs-lookup"><span data-stu-id="639d9-131">If you see one or more of the following symptoms on your computer, you could have a serious system memory issue:</span></span>

- <span data-ttu-id="639d9-132">Utilisation de mémoire élevée lorsque plusieurs applications de grande taille sont en cours d’exécution simultanée.</span><span class="sxs-lookup"><span data-stu-id="639d9-132">High memory use when multiple large applications are running simultaneously.</span></span>
- <span data-ttu-id="639d9-133">Performances du système ralenties ou applications en suspension.</span><span class="sxs-lookup"><span data-stu-id="639d9-133">Slow system performance or applications hanging.</span></span>
- <span data-ttu-id="639d9-134">Une utilisation globale de la mémoire système de 90 % ou plus, au moins, pour toutes les applications.</span><span class="sxs-lookup"><span data-stu-id="639d9-134">Sustained overall system memory usage of 90% or higher across all apps.</span></span> <span data-ttu-id="639d9-135">Avec ce volume d’utilisation de la mémoire, Teams doit donner de la mémoire à d’autres applications et charges de travail.</span><span class="sxs-lookup"><span data-stu-id="639d9-135">With this amount of memory usage, Teams should be giving memory back to other apps and workloads.</span></span> <span data-ttu-id="639d9-136">Une utilisation durable de la mémoire à 90 % peut signifier que Teams ne donne pas de mémoire au système, ce qui indique un problème.</span><span class="sxs-lookup"><span data-stu-id="639d9-136">Sustained memory usage of 90% could mean Teams isn't giving memory back to the system, which indicates a problem.</span></span>

<span data-ttu-id="639d9-137">Les images suivantes illustrent des exemples d’affichages dans le Gestionnaire des tâches lorsque l’utilisation de la mémoire système est anormalement élevée.</span><span class="sxs-lookup"><span data-stu-id="639d9-137">The following images show examples of views in Task Manager when system memory usage is abnormally high.</span></span>

![Affichage Utilisation de la mémoire Teams dans le Gestionnaire des tâches](media/teams-memory-high-mem-process-list.png)

![Graphique de l’utilisation de la mémoire Teams dans le Gestionnaire des tâches](media/teams-memory-high-mem-process-list2.png)
