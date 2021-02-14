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
# <a name="how-microsoft-teams-uses-memory"></a>Utilisation de la mémoire par Microsoft Teams

Certains utilisateurs de Microsoft Teams ont des questions sur la façon dont Teams utilise la mémoire. Cet article décrit comment la mémoire est utilisée par Teams et pourquoi l’application de bureau Teams (application) et l’application web Teams n’empêchent pas les autres applications et charges de travail sur le même ordinateur d’avoir suffisamment de mémoire pour fonctionner de manière optimale. Teams est conçu pour utiliser la technologie web moderne. Pour ce faire, le client de bureau Teams a été développé sur Electron, qui utilise Chromium pour le rendu. Il s’agit du même moteur de rendu derrière la plupart des navigateurs les plus populaires à ce jour, notamment Microsoft Edge et Chrome.

## <a name="how-teams-works"></a>Fonctionnement de Teams

La conception de Teams sur Electron permet un développement plus rapide, ainsi que la parité entre les versions de Teams sur différents systèmes d’exploitation (Windows, Mac et Linux). Cette parité est possible, car Electron et Chromium conservent une base de code similaire dans toutes les versions. Un autre avantage de cette architecture est qu’il existe un profil d’utilisation de mémoire similaire entre l’application web Teams et la version de bureau. L’application web et les versions de bureau utilisent la mémoire de la même façon qu’un navigateur l’utiliserait. Des informations supplémentaires sur Electron sont disponibles sur [leur site web.](https://electronjs.org/)

Pour plus [d’informations, voir Utilisation de la mémoire Chromium](https://www.chromium.org/developers/memory-usage-backgrounder) et Concepts clés [dans la mémoire Chrome.](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md)

L’image suivante illustre les utilisations de la mémoire côte à côte de l’application de bureau Teams pour Windows et de l’application Web Teams (dans cet exemple, qui s’exécute dans Google Chrome).

![Utilisation de la mémoire Teams pour l’application de bureau et l’application Web](media/teams-memory-clientweb.png)

## <a name="memory-usage-in-teams"></a>Utilisation de la mémoire dans Teams

Il est important  de comprendre le comportement attendu de Teams en ce qui concerne la mémoire système et de connaître les symptômes des problèmes de mémoire système véritablement problématiques.

### <a name="expected-memory-usage-by-teams"></a>Utilisation attendue de la mémoire par Teams

Que vous exécutez l’application de bureau Teams ou l’application web Teams, Chromium détecte la quantité de mémoire système disponible et utilise suffisamment cette mémoire pour optimiser l’expérience de rendu. Lorsque d’autres applications ou services nécessitent de la mémoire système, Chromium en fait la mémoire pour ces processus. Chromium tunes Teams memory usage on angoing basis in order to optimize Teams performance without impacting anything else running.

Ainsi, les charges de travail Chromium similaires peuvent utiliser diverses quantités de mémoire, selon la quantité de mémoire système disponible.

Le graphique suivant illustre l’utilisation de la mémoire par Teams sur quatre systèmes distincts, chacun avec une quantité différente de mémoire disponible. Chacun des systèmes traite des charges de travail similaires (les mêmes applications sont ouvertes et en cours d’exécution).

![Utilisation de la mémoire Teams dans différents systèmes](media/teams-memory-usage.png)

Lorsque les ordinateurs ont plus de mémoire, Teams utilise cette mémoire. Dans les systèmes où la mémoire est en place, Teams en utilise moins.

### <a name="symptoms-of-system-memory-issues"></a>Symptômes de problèmes de mémoire système

Si vous constatez un ou plusieurs des symptômes suivants sur votre ordinateur, vous pouvez avoir un problème sérieux de mémoire système :

- Utilisation de mémoire élevée lorsque plusieurs applications de grande taille sont en cours d’exécution simultanée.
- Performances du système ralenties ou applications en suspension.
- Une utilisation globale de la mémoire système de 90 % ou plus, au moins, pour toutes les applications. Avec ce volume d’utilisation de la mémoire, Teams doit donner de la mémoire à d’autres applications et charges de travail. Une utilisation durable de la mémoire à 90 % peut signifier que Teams ne donne pas de mémoire au système, ce qui indique un problème.

Les images suivantes illustrent des exemples d’affichages dans le Gestionnaire des tâches lorsque l’utilisation de la mémoire système est anormalement élevée.

![Affichage Utilisation de la mémoire Teams dans le Gestionnaire des tâches](media/teams-memory-high-mem-process-list.png)

![Graphique de l’utilisation de la mémoire Teams dans le Gestionnaire des tâches](media/teams-memory-high-mem-process-list2.png)
