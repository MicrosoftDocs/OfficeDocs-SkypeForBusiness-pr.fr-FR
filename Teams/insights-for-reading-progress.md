---
title: Comprendre les recommandations d’Insights pour la lecture de la progression
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Découvrez comment les données Insights sont utilisées dans la progression de la lecture pour améliorer les compétences en lecture des étudiants.
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-edu
appliesto:
- Microsoft Teams
ms.openlocfilehash: 30a98c9ccda13635a6c3fccaae41e8869b8cfce5
ms.sourcegitcommit: 07761c26b53d92fc36b82cab7b3e38a6de4ff945
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/02/2022
ms.locfileid: "67157876"
---
# <a name="understand-insights-for-reading-progress-recommendations"></a>Comprendre les recommandations d’Insights pour la lecture de la progression

Cet article s’adresse aux administrateurs informatiques de l’éducation qui souhaitent comprendre comment les données Insights sont utilisées pour les recommandations de progression de la lecture.

Insights permet aux enseignants de suivre la maîtrise de la lecture de leurs étudiants à l’aide de La progression de la lecture, un outil qui enregistre les étudiants qui lisent à haute voix et détecte automatiquement les erreurs.

La progression de la lecture fournit les types suivants d’affectations de défis de lecture :

- **Mots contextuels** : pratiquez les mots recommandés en fonction des mots que les étudiants ont mal dénoncés dans les devoirs de progression de lecture passés.
- **Mots corrélés** : pratiquez les mots recommandés en fonction d’erreurs courantes pour les étudiants ayant le même type de difficultés de lecture.

Pour obtenir des conseils sur l’utilisation d’Insights pour la progression de la lecture, consultez [Créer des devoirs de défi de progression de la lecture avec Insights](https://support.microsoft.com/topic/c2f8f4c0-69d5-4302-b3a5-ee4dfb7a8ffe).

## <a name="how-does-microsoft-recommend-correlated-words"></a>Comment Microsoft recommande-t-il des mots corrélés ?

Les mots corrélés sont des mots personnalisés et recommandés que Insights for Education a identifiés comme difficiles pour les autres étudiants qui partagent des modèles de lecture similaires.

Les mots corrélés sont basés sur une technique de Machine Learning appelée **filtrage collaboratif**.

- Insights analyse les données de lecture des étudiants dans les classes qui partagent votre zone géographique et votre langue pour identifier des clusters de mots difficiles pour les étudiants.

- Compte tenu d’un ensemble de mots difficiles, Insights identifie également des clusters similaires et les utilise pour recommander d’autres mots aux étudiants pour une pratique ciblée.

## <a name="does-microsoft-keep-students-data-private-and-secure"></a>Microsoft conserve-t-il les données des étudiants privées et sécurisées ?

Microsoft s’engage à utiliser les données de manière responsable et éthique.

Voici quelques-unes des mesures prises pour créer cette fonctionnalité :

- Les analyses des données des étudiants sont conçues de manière visuelle, ce qui signifie que Microsoft n’a pas accès aux données de lecture des étudiants, uniquement aux résultats de l’analyse.

- Les administrateurs de locataires peuvent refuser le processus d’analyse des données en désactivant le [bouton bascule Inférences avancées](class-insights.md#turn-on-and-off-advanced-inferences-in-insights).

- Les mots inappropriés sont filtrés des listes de recommandations de **mots corrélés** . Cette opération s’effectue à l’aide d’une combinaison de techniques de science des données et de blocage de mots problématiques connus. Toutefois, ce processus n’est pas une preuve d’erreur. Les enseignants doivent passer en revue les recommandations.

## <a name="what-are-the-limitations-of-insights-word-recommendations"></a>Quelles sont les limitations des recommandations de mots d’Insights ?

- Les recommandations Word relatives à la progression de la lecture sont actuellement prises en charge dans [ces langues](https://support.microsoft.com/topic/getting-started-with-reading-progress-in-teams-7617c11c-d685-4cb7-8b75-3917b297c407#ID0EDD=Supported_Languages).

- Les mots corrélés sont présentés uniquement dans les classes d’au moins cinq étudiants qui ont soumis des devoirs de progression de lecture.

- Insights peut ne pas recommander de nouveaux mots dans les cas où il n’y a pas d’étudiants avec des modèles d’erreur similaires, mais pas identiques.
