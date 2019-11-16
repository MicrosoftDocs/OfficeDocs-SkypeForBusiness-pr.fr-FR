---
title: Packages de stratégie de Microsoft teams pour les administrateurs EDU
author: jambirk
ms.author: jambirk
manager: serdars
ms.reviewer: prkuch
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
f1keywords: ms.teamsadmincenter.policypackages.overview
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser et gérer des packages de stratégie dans Microsoft Teams.
ms.openlocfilehash: a49ab725ff0042b75afca9b1f9b4d7d9655c34b7
ms.sourcegitcommit: 70bf1669442bbb50cb293c86d6a0c80fb3b2b55a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2019
ms.locfileid: "38676252"
---
# <a name="microsoft-teams-policy-packages-for-edu-admins"></a>Packages de stratégie de Microsoft teams pour les administrateurs EDU

Dans Microsoft Teams, vous pouvez attribuer des stratégies et des paramètres de stratégie prédéfinis aux utilisateurs ayant des rôles similaires dans votre établissement. Les packages de stratégie simplifient la simplification et permettent de garantir une cohérence lors de la gestion des stratégies. Dans la pratique normale, vous affectez à chacun de vos utilisateurs un package de stratégie et, selon le cas, redéfinissez les stratégies dans chaque package selon les besoins de ce groupe d’utilisateurs. Lorsque vous mettez à jour les paramètres d’un package, tous les utilisateurs attribués à ce package sont modifiés comme une mise à jour en bloc.

En général, les établissements d’enseignement présentent de nombreux types d’utilisateurs ayant des besoins uniques, en fonction de l’âge et de la maturité des étudiants. Par exemple, vous souhaiterez peut-être octroyer un accès complet aux enseignants et aux membres du personnel de Microsoft Teams, mais vous souhaitez limiter les fonctionnalités de Microsoft teams aux étudiants pour encourager un environnement d’apprentissage sécurisé et ciblé. Vous pouvez utiliser des packages de stratégie pour personnaliser les paramètres en fonction de vos besoins concernant différentes cohortes dans votre communauté scolaire.

## <a name="what-is-a-policy-package"></a>Qu’est-ce qu’un package de stratégie ?

Les packages de stratégie vous permettent de contrôler les fonctionnalités de Microsoft Teams, qui permettent ou restreignent l’utilisation de Microsoft teams pour des ensembles spécifiques de personnes de votre organisation. Chaque package de stratégie est conçu à l’aide d’un rôle d’utilisateur et comprend des stratégies et des paramètres de stratégie prédéfinis qui prennent en charge les activités typiques pour ce rôle.

Packages de stratégie prédéfinis pour :
- Messagerie
- Réunions
- Configuration de l’application
- Appels
- Événements en direct

Microsoft teams inclut actuellement les packages de stratégie suivants :

|Nom du package répertorié dans le centre d’administration Microsoft teams |La meilleure utilisation pour  |Description |
|:--- |:--- |:--- |
|Education_Teacher| Enseignants et membres du personnel enseignant| Utilisez ce jeu de stratégies et de paramètres de stratégie pour permettre aux enseignants et au personnel de votre organisation d’accéder à des conversations, des appels et des réunions par le biais de Microsoft Teams. |
|Education_PrimaryStudent | Premiers étudiants du classement scolaire  | Plus vous avez de personnes âgées de plus de ans au sein de votre établissement d’enseignement. Utilisez ce jeu de stratégies et de paramètres de stratégie pour limiter les fonctionnalités telles que la création et la gestion des réunions, la gestion des discussions et les appels privés. |
|Education_SecondaryStudent| Étudiants secondaires âgés | École secondaire les étudiants âgés de votre établissement peuvent nécessiter davantage de limites dans Microsoft Teams. Utilisez ce jeu de stratégies et de paramètres de stratégie pour limiter les fonctionnalités telles que la création et la gestion des réunions, la gestion des discussions et les appels privés. |
|Education_HigherEducationStudent | Élèves plus scolaires | Les étudiants de votre éducation au sein de votre intuition peuvent avoir besoin d’autant de limitations que celles de jeunes étudiants, mais certaines limitations peuvent être recommandées. Vous pouvez utiliser ce jeu de stratégies et de paramètres de stratégie pour donner accès à des conversations, des appels et des réunions au sein de votre organisation, mais limiter la façon dont vos étudiants utilisent Microsoft teams avec des participants externes. |
|||

Chaque stratégie individuelle dispose du nom du package de stratégie, ce qui vous permet d’identifier facilement les stratégies liées à un package de stratégie. Par exemple, lorsque vous attribuez le package de stratégie de Education_Teacher aux enseignants de votre établissement scolaire, une stratégie nommée Education_Teacher est créée pour chaque stratégie dans le package.

![Capture d’écran du package de stratégie Education_Teacher](media/policy-packages-education_teacher.png)

> [!NOTE]
> Si vous décidez que les enseignants et le personnel de support administratif doivent disposer d’une stratégie différente, vous pouvez réutiliser un package existant : Identifiez un package que vous n’utilisez pas actuellement et modifiez les paramètres de manière à ce qu’il soit approprié pour ce groupe. Vous devrez peut-être vous faire savoir quel est le groupe dont vous avez besoin pour la réaffectation d’un package.

## <a name="why-use-policy-packages"></a>Pourquoi utiliser des packages de stratégie

Si votre établissement possède des centaines, voire des milliers d’utilisateurs, vous vous demandez peut-être : « pourquoi prendre le temps d’assigner un package ou un autre à tous les utilisateurs ? »

L’attribution de packages à des centaines d’utilisateurs représente un investissement dans des activités hors projet, sans question. Un sujet important relatif aux placements est qu’ils paient au fil du temps, plutôt que immédiatement.

Dans un environnement éducatif, il existe de nombreux utilisateurs ayant des rôles identiques ou similaires. Vous dépensez moins d’efforts lorsque vous gérez leur interface utilisateur de la même manière. Groupe packages ensemble de stratégies spécifiques aux différents rôles de l’établissement. Les utilisateurs disposant d’une licence similaire, mais de rôles différents, peuvent avoir des stratégies pertinentes affectées en fonction de leur rôle, ce qui est plus efficace que de peaufiner des stratégies pour des utilisateurs individuels.

Une fois que tous les utilisateurs de l’établissement sont triés dans les groupes et qu’ils ont appliqué des packages, la gestion de ces derniers est une question de modification des paramètres de package une seule fois pour tous les utilisateurs attribués au package. Vous pouvez choisir d’affiner les stratégies au sein d’un package avant ou après l’affectation des utilisateurs au package.

Pour obtenir des instructions détaillées sur l’attribution d’un package à des utilisateurs individuels, voir [gérer les packages de stratégie dans Microsoft teams](manage-policy-packages.md) et gérer et mettre à jour les stratégies liées à chaque package.
