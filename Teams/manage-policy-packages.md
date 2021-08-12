---
title: Gérer les packages de stratégie dans Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: sekrantz, aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policypackages.overview
- seo-marvel-apr2020
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser et gérer des packages de stratégie dans Microsoft Teams pour simplifier, rationaliser et contribuer à assurer la cohérence lors de la gestion des stratégies pour des groupes d’utilisateurs.
ms.openlocfilehash: 2fd892bc440996c7c1f000402122ad268a402ebb6bf382672813efa296de819f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341783"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a>Gérer les packages de stratégie dans Microsoft Teams

Un package de stratégie dans Microsoft Teams est un ensemble de stratégies et de paramètres de stratégie prédéfincis que vous pouvez attribuer aux utilisateurs qui ont des rôles similaires dans votre organisation. Nous avons créé des packages de stratégie pour simplifier, simplifier et contribuer à assurer la cohérence lors de la gestion des stratégies pour des groupes d’utilisateurs au sein de votre organisation.  

Vous pouvez utiliser les [packages de stratégie inclus](#policy-packages-included-in-teams) dans Teams ou créer [vos propres packages de stratégie personnalisés.](#custom-policy-packages)

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="Capture d’écran de la page Packages de stratégie dans le Centre d’administration":::

Vous pouvez personnaliser les paramètres des stratégies dans un package de stratégie en fonction des besoins de vos utilisateurs. Lorsque vous modifiez les paramètres des stratégies dans un package, tous les utilisateurs affectés à ce package obtiennent les paramètres mis à jour. Vous gérez les packages de stratégie à l’aide Microsoft Teams centre d’administration ou PowerShell.

> [!NOTE]
> Chaque utilisateur aura besoin du module add-on Communications avancées pour recevoir une attribution de package de stratégie personnalisée. Pour plus d’informations, [voir le module complémentaire Communications](/microsoftteams/teams-add-on-licensing/advanced-communications)avancées pour Microsoft Teams .

## <a name="what-is-a-policy-package"></a>Qu’est-ce qu’un package de stratégie ?

Les packages de stratégie vous permettent de contrôler Teams fonctionnalités que vous souhaitez autoriser ou restreindre pour des ensembles spécifiques de personnes au sein de votre organisation. Chaque package de stratégie dans Teams est conçu autour d’un rôle d’utilisateur et inclut des stratégies et des paramètres de stratégie prédéfinés qui la prise en charge des activités de collaboration et de communication qui sont typiques pour ce rôle.

Les packages de stratégies peuvent être Teams types de stratégie suivants :

- Stratégie de messagerie
- Stratégie de réunion
- Stratégie de configuration d’application
- Stratégie d’Appel
- Stratégie d’événements en direct

## <a name="policy-packages-included-in-teams"></a>Packages de stratégie inclus dans Teams

Teams inclut actuellement les packages de stratégie suivants.

| Nom du package | Description |
|---------|---------|
|Éducation (étudiant de l’enseignement supérieur)    |Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux étudiants de l’enseignement supérieur.|
|Éducation (étudiant de l’école primaire)   |Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux étudiants du primaire.|
|Éducation (étudiant de l’école secondaire)    |Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux étudiants secondaires.         |
|Éducation (enseignant)    |Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux enseignants.      |
|Éducation (enseignant de l’école primaire utilisant l’apprentissage à distance)    |Crée un ensemble de stratégies qui s’appliquent aux enseignants du primaire pour optimiser la sécurité et la collaboration des étudiants lors de l’utilisation de l’apprentissage à distance.      |
|Éducation (étudiant de l’école primaire utilisant l’apprentissage à distance)    |Crée un ensemble de stratégies qui s’appliquent aux étudiants du primaire pour optimiser la sécurité et la collaboration des étudiants lors de l’utilisation de l’apprentissage à distance.      |
|Gestionnaire de poste |Crée un ensemble de stratégies et applique ces paramètres aux responsables de la sécurité dans votre organisation. |
|Travailleur de l’avant |Crée un ensemble de stratégies et applique ces paramètres aux employés de votre organisation. |
|Professionnel de la santé médicale  |Crée un ensemble de stratégies et de paramètres de stratégie qui donnent aux travailleurs de l’urgence, tels que les auxiliaires de santé inscrits, les médecins, les personnes autorisées à facturer et les travailleurs sociaux un accès complet à la conversation, aux appels, à la gestion des équipes et aux réunions. |
|Travailleurs de l’information sur la santé  |Crée un ensemble de stratégies et de paramètres de stratégie qui donnent aux travailleurs de l’information, tels que le personnel de l’information, le personnel informatique, le personnel financier et les responsables de la mise en conformité, un accès total à la conversation, aux appels et aux réunions.|
|Salle de soins de santé  |Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux salles de patients de votre organisation de santé.|
|Petite et moyenne entreprise (Business Voice) |Crée une stratégie de configuration d’application qui inclut les applications pour une expérience vocale d’entreprise.|
|Petite et moyenne entreprise (sans Business Voice) |Crée une stratégie de configuration d’application pertinente pour les petites et moyennes entreprises Teams utilisateurs (expérience non Business Voice).
|Responsable de la sécurité publique   |Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux agents de sécurité publique de votre organisation.|

> [!NOTE]
> Nous ajouterons d’autres packages de stratégie dans les prochaines Teams, donc recherchez les informations les plus à jour.  

Chaque stratégie individuelle est associée au nom du package de stratégie afin que vous pouvez facilement identifier les stratégies liées à un package de stratégie.
Par exemple, lorsque vous affectez le package de stratégie Éducation (enseignant) aux enseignants de votre établissement scolaire, une stratégie nommée Education_Teacher est créée pour chaque stratégie du package.

![Capture d’écran du package de stratégie Éducation (enseignant)](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a>Packages de stratégie personnalisés

**Les packages de stratégie personnalisés ne sont pas encore disponibles pour Cloud de la communauté du secteur public (Cloud de la communauté du secteur public)**

Les packages de stratégie personnalisés vous permet de regrouper votre propre ensemble de stratégies pour les utilisateurs ayant des rôles similaires dans votre organisation. Créez vos propres packages de stratégie en ajoutant les types de stratégie et les stratégies dont vous avez besoin.

Pour créer un package de stratégie personnalisé :

1. Dans le navigation gauche du centre d’administration Microsoft Teams, sélectionnez **packages** de stratégie, puis cliquez sur **Ajouter.**

    :::image type="content" source="media/policy-packages-add.png" alt-text="Capture d’écran du bouton Ajouter sur la page Packages de stratégie dans le Centre d’administration":::

2. Entrez un nom et une description pour votre package.

    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="Capture d’écran de l’ajout d’un nouveau package de stratégie personnalisé":::

3. Sélectionnez les types de stratégie et les noms de stratégie à inclure dans le package.

4. Cliquez sur **Save (Enregistrer)**.

## <a name="how-to-use-policy-packages"></a>Utilisation des packages de stratégie

L’exemple suivant décrit l’utilisation des packages de stratégie dans votre organisation.

![Vue d’ensemble de l’utilisation des packages de stratégie](media/manage-policy-packages-overview.png)

- **[Affichage](#view-the-settings-of-a-policy-in-a-policy-package)**: afficher les stratégies dans un package de stratégie. Ensuite, affichez les paramètres de chaque stratégie dans un package avant d’attribuer le package. Assurez-vous que vous comprenez chaque paramètre. Déterminez si les valeurs prédéfinies sont appropriées pour votre organisation ou si vous devez les modifier pour qu’elles soient plus restrictives ou plus restrictives en fonction des besoins de votre organisation.

    Si une stratégie est supprimée, vous pouvez toujours afficher les paramètres, mais vous ne pourrez pas modifier les paramètres. Une stratégie supprimée est re-créée avec les paramètres prédéfincis lorsque vous affectez le package de stratégie.

- **[Personnaliser](#customize-policies-in-a-policy-package)**: personnaliser les paramètres des stratégies dans le package de stratégie pour répondre aux besoins de votre organisation.

- **[Assign :](#assign-a-policy-package)** assigner le package de stratégie aux utilisateurs.  

> [!NOTE]
> Vous pouvez également modifier les paramètres des stratégies dans un package de stratégie après avoir attribué un package. Toutes les modifications apportées aux paramètres de stratégie sont automatiquement appliquées aux utilisateurs affectés au package.

Voici les étapes à suivre pour afficher, affecter et personnaliser des packages de stratégie dans le centre d’administration Microsoft Teams de gestion.

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a>Afficher les paramètres d’une stratégie dans un package de stratégie

1. Dans le navigation gauche du centre d’administration Microsoft Teams, sélectionnez **Packages** de stratégie, puis sélectionnez un package de stratégie en cliquant à gauche du nom du package.

2. Cliquez sur la stratégie à afficher.

### <a name="customize-policies-in-a-policy-package"></a>Personnaliser des stratégies dans un package de stratégie

Vous pouvez modifier les paramètres d’une stratégie via la page **Packages** de stratégie ou en allant directement à la page de stratégie dans le centre d Microsoft Teams’administration.

1. Dans le volet de navigation gauche du centre d’administration de Microsoft Teams, effectuez l’une des actions suivantes :
    - Cliquez **sur Packages de stratégie,** puis sélectionnez le package de stratégie en cliquant à gauche du nom du package.
    - Cliquez sur le type de stratégie.  Par exemple, cliquez sur **Stratégies de messagerie.**

2. Sélectionnez la stratégie que vous souhaitez modifier. Les stratégies liées à un package de stratégies portent le même nom que le package de stratégies.

3. A apporté les modifications que vous souhaitez, puis cliquez sur **Enregistrer.**

### <a name="assign-a-policy-package"></a>Affecter un package de stratégies

Vous pouvez affecter un package de stratégie à un utilisateur individuel, à un groupe ou à un lot d’utilisateurs. Pour plus d’informations sur l’attribution de packages de stratégie, voir Attribuer des packages de [stratégie aux utilisateurs et groupes.](assign-policy-packages.md)

## <a name="related-topics"></a>Voir aussi

- [Affecter des packages de stratégies](assign-policy-packages.md)
- [Teams packages de stratégie pour les administrateurs edu](policy-packages-edu.md)
- [Teams des packages de stratégie pour les soins de santé](policy-packages-healthcare.md)
- [Teams packages de stratégie pour le gouvernement](policy-packages-gov.md)
