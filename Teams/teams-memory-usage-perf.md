---
title: Utilisation de la mémoire par Microsoft teams
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
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6dcbe03851b8dbb31cd0bd6f1b580913d4dc683d
ms.sourcegitcommit: f017e38095098d4d28c71241dddac53538be79d7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/24/2020
ms.locfileid: "41506901"
---
# <a name="how-microsoft-teams-uses-memory"></a>Utilisation de la mémoire par Microsoft teams

Certains utilisateurs de Microsoft teams ont des questions sur l’utilisation de la mémoire par Teams. Cet article décrit la façon dont la mémoire est utilisée par teams et pourquoi l’application de bureau Teams (application) et l’application Web teams n’empêchent pas d’autres applications et charges de travail sur le même ordinateur d’avoir suffisamment de mémoire pour fonctionner de manière optimale. Teams est conçu pour utiliser la technologie Web moderne. Pour ce faire, le client de bureau teams a été développé sur Electron, qui utilise le chrome pour le rendu. Il s’agit du même moteur de rendu que sur la plupart des navigateurs les plus populaires du jour, y compris les périphériques Edge et chrome.

## <a name="how-teams-works"></a>Fonctionnement d’teams

Les équipes spécialisées en matière d’électrons permettent un développement plus rapide et disposent également de la parité entre les versions d’équipe sur différents systèmes d’exploitation (Windows, Mac et Linux). Cette parité est possible, car le son pour le son de type « Electron » et « chrome » entretiennent une base de code similaire pour toutes les versions Un autre avantage de cette architecture est le profil d’utilisation de mémoire similaire entre Team Web App et la version de bureau. L’application Web et les versions de bureau utilisent la mémoire de manière similaire à la façon dont un navigateur l’utiliserait. Des informations supplémentaires sur l’électron sont disponibles sur [leur site Web](https://electronjs.org/).

Pour plus d’informations, voir utilisation de la [mémoire de chrome](https://www.chromium.org/developers/memory-usage-backgrounder) et [concepts clés de la mémoire chrome](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md) .

L’image ci-dessous illustre l’utilisation de la mémoire côte à côte de l’application de bureau teams pour Windows et de l’application Web Teams (dans cet exemple, exécutée dans Google Chrome).

![Application de bureau teams et utilisation de la mémoire Web App](media/teams-memory-clientweb.png)

## <a name="memory-usage-in-teams"></a>Utilisation de la mémoire dans teams

Il est important de comprendre le comportement *attendu* d’teams lorsqu’il s’agit de la mémoire système et de connaître les symptômes de véritables problèmes de mémoire système.

### <a name="expected-memory-usage-by-teams"></a>Utilisation de la mémoire prévue par teams

Que vous utilisiez l’application de bureau teams ou Team Web App, chrome détecte la quantité de mémoire système disponible et utilise suffisamment de mémoire pour optimiser l’expérience de rendu. Lorsque d’autres applications ou services nécessitent une mémoire système, le chrome libère de la mémoire pour ces processus. Le chrome ajuste l’utilisation de la mémoire aux équipes de façon continue pour optimiser les performances des équipes sans avoir à influer sur tout autre élément en cours d’exécution.

De cette façon, les charges de travail similaires peuvent utiliser des quantités variables de mémoire, en fonction de la quantité de mémoire système disponible.

Le graphique suivant illustre l’utilisation de la mémoire par teams sur quatre systèmes distincts, chacun avec des quantités différentes de mémoire disponibles. Chacun des systèmes traite des charges de travail similaires (les mêmes applications sont ouvertes et exécutées).

![Utilisation de la mémoire par teams sur différents systèmes](media/teams-memory-usage.png)

Lorsque les ordinateurs disposent de plus de mémoire, teams utilise cette mémoire. Dans les systèmes dont la mémoire est faible, teams utilisera moins. 

### <a name="symptoms-of-system-memory-issues"></a>Symptômes liés aux problèmes de mémoire système

Si vous voyez un ou plusieurs des problèmes suivants sur votre ordinateur, vous pouvez rencontrer des problèmes de mémoire système importants :

- Utilisation de la mémoire haute lorsque plusieurs applications de grande taille s’exécutent simultanément.
- Baisse des performances du système ou applications suspendues.
- Utilisation de la mémoire système globale de 90% ou une valeur supérieure dans toutes les applications. En ce qui concerne l’utilisation de la mémoire, teams doit remettre en mémoire d’autres applications et charges de travail. L’utilisation de la mémoire continue de 90% peut signifier que Teams ne donne pas de mémoire au système, ce qui indique un problème.

Les images suivantes montrent des exemples d’affichages dans le gestionnaire des tâches lorsque l’utilisation de la mémoire système est anormalement élevée.

![Affichage utilisation de la mémoire dans teams du gestionnaire des tâches](media/teams-memory-high-mem-process-list.png)

![Graphique utilisation de la mémoire dans teams dans le gestionnaire des tâches](media/teams-memory-high-mem-process-list2.png)
