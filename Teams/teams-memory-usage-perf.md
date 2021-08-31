---
title: Utilisation de la mémoire par Microsoft Teams
author: msdmaguire
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: En savoir Microsoft Teams’utilisation de la mémoire système et pourquoi l’utilisation de mémoire est la même entre l’application de bureau et l’application web.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: 70862d2d48d98517365b35d05ccd36dd9cb4ffd3
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58734033"
---
# <a name="how-microsoft-teams-uses-memory"></a>Utilisation de la mémoire par Microsoft Teams

Certains utilisateurs Microsoft Teams des questions sur la façon dont Teams utilise la mémoire. Cet article décrit comment la mémoire est utilisée par Teams et pourquoi l’application de bureau Teams (application) et l’application web Teams n’empêchent pas les autres applications et charges de travail sur le même ordinateur d’avoir suffisamment de mémoire pour s’exécuter de manière optimale. Teams est conçu pour utiliser la technologie web moderne. Pour ce faire, le client Teams bureau a été développé sur Electron, qui utilise des Chromium pour le rendu. Il s’agit du même moteur de rendu derrière la plupart des navigateurs les plus populaires à ce jour, notamment Microsoft Edge et Chrome.

## <a name="how-teams-works"></a>Fonctionnement des Teams

Teams conception sur Electron permet un développement plus rapide, ainsi que la parité entre les versions Teams sur différents systèmes d’exploitation (Windows, Mac et Linux). Cette parité est possible, car Electron et Chromium maintenir une base de code similaire dans toutes les versions. Un autre avantage de cette architecture est qu’il existe un profil d’utilisation de mémoire semblable entre l’application web Teams et la version de bureau. L’application web et les versions de bureau utilisent la mémoire de la même façon qu’un navigateur l’utiliserait. Des informations supplémentaires sur Electron sont disponibles sur [leur site web.](https://electronjs.org/)

Voir [Chromium utilisation de la mémoire et](https://www.chromium.org/developers/memory-usage-backgrounder) les concepts clés de la mémoire [Chrome](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md) pour plus d’informations.

L’image suivante illustre les utilisations de la mémoire côte à côte de l’application de bureau Teams pour Windows et de l’application web Teams (dans cet exemple, s’exécutant dans Google Chrome).

![Teams’utilisation de la mémoire pour l’application de bureau et l’application web.](media/teams-memory-clientweb.png)

## <a name="memory-usage-in-teams"></a>Utilisation de la mémoire dans Teams

Il est important  de comprendre le comportement attendu d’Teams en ce qui concerne la mémoire système, et de connaître les symptômes des problèmes de mémoire du système véritablement problématiques.

### <a name="expected-memory-usage-by-teams"></a>Utilisation attendue de la mémoire par Teams

Que vous exécutez l’application de bureau Teams ou l’application web Teams, Chromium détecte la quantité de mémoire système disponible et utilise cette quantité de mémoire pour optimiser l’expérience de rendu. Lorsque d’autres applications ou services nécessitent de la mémoire système, Chromium à ces processus. Chromium optimiser Teams l’utilisation continue de la mémoire afin d’optimiser Teams performances sans impact sur les autres opérations en cours d’exécution.

Ainsi, des charges Chromium de travail peuvent utiliser diverses quantités de mémoire, selon la quantité de mémoire système disponible.

Le graphique suivant illustre l’utilisation de la mémoire par Teams sur quatre systèmes distincts, chacun avec une quantité différente de mémoire disponible. Chacun des systèmes traite des charges de travail similaires (les mêmes applications sont ouvertes et en cours d’exécution).

![Teams’utilisation de la mémoire dans différents systèmes.](media/teams-memory-usage.png)

Lorsque les ordinateurs ont plus de mémoire, Teams’utilisera cette mémoire. Dans les systèmes où la mémoire est vive, Teams en utiliseront moins.

### <a name="symptoms-of-system-memory-issues"></a>Symptômes de problèmes de mémoire système

Si vous constatez un ou plusieurs des symptômes suivants sur votre ordinateur, vous pouvez avoir un problème sérieux de mémoire système :

- Utilisation de mémoire élevée lorsque plusieurs applications de grande taille sont en cours d’exécution simultanée.
- Performances du système ralenties ou applications en suspension.
- Une utilisation globale de la mémoire système de 90 % ou plus, au moins, pour toutes les applications. Avec ce volume d’utilisation de la mémoire, Teams doit donner de la mémoire à d’autres applications et charges de travail. Une utilisation durable de la mémoire à 90 % Teams ne donne pas de mémoire au système, ce qui indique un problème.

Les images suivantes illustrent des exemples d’affichages dans le Gestionnaire des tâches lorsque l’utilisation de la mémoire système est anormalement élevée.

![Teams’utilisation de la mémoire dans le Gestionnaire des tâches.](media/teams-memory-high-mem-process-list.png)

![Teams de l’utilisation de la mémoire dans le Gestionnaire des tâches.](media/teams-memory-high-mem-process-list2.png)
