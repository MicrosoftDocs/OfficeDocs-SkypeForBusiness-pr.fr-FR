---
title: Gérer les packages de stratégie dans Microsoft Teams
author: HowlinWolf-92
ms.author: v-mahoffman
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
ms.localizationpriority: medium
search.appverid: MET150
description: Découvrez comment utiliser et gérer des packages de stratégie dans Microsoft Teams simplifier, rationaliser et offrir une cohérence dans le cadre de la gestion des stratégies pour des groupes d’utilisateurs.
ms.openlocfilehash: 771b4f2e0e62f9721bcd135e1d01dc4be3ce7285
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60868493"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a>Gérer les packages de stratégie dans Microsoft Teams

Un package de stratégie dans Microsoft Teams est un ensemble de stratégies et de paramètres de stratégie prédéfinis que vous pouvez affecter aux utilisateurs ayant des rôles similaires dans votre organisation. Nous avons créé des packages de stratégies pour simplifier, rationaliser et offrir une cohérence dans le cadre de la gestion des stratégies pour des groupes d’utilisateurs au sein de votre organisation.  

Vous pouvez utiliser les [packages de stratégie inclus dans Teams](#policy-packages-included-in-teams) créer vos propres [packages de stratégie personnalisés.](#custom-policy-packages)

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="Capture d’écran de la page Packages de stratégie dans le Centre d’administration.":::

Vous pouvez personnaliser les paramètres des stratégies dans un package de stratégies pour répondre aux besoins de vos utilisateurs. Lorsque vous modifiez les paramètres des stratégies dans un package, tous les utilisateurs affectés à ce package obtiennent les paramètres mis à jour. Vous gérez les packages de stratégie à l’aide Microsoft Teams centre d’administration ou PowerShell.

> [!NOTE]
> Chaque utilisateur aura besoin du module complémentaire Communications avancées pour recevoir une attribution de package de stratégie personnalisée. Pour plus d’informations, consultez [Module complémentaire Communications avancées pour Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).

## <a name="what-is-a-policy-package"></a>Qu’est-ce qu’un package de stratégie ?

Les packages de stratégie vous permettent de Teams fonctionnalités que vous voulez autoriser ou restreindre pour des ensembles spécifiques de personnes au sein de votre organisation. Chaque package de stratégie dans Teams est conçu autour d’un rôle d’utilisateur et inclut des stratégies et paramètres de stratégie prédéfinés qui supportent les activités de collaboration et de communication classiques pour ce rôle.

Les packages de stratégies prisent en charge Teams types de stratégies suivants :

- Stratégie de messagerie
- Stratégie de réunion
- Stratégie de configuration de l’application
- Stratégie d’Appel
- Stratégie d’événements en direct

## <a name="policy-packages-included-in-teams"></a>Packages de stratégie inclus dans Teams

Teams inclut actuellement les packages de stratégie suivants.

| Nom du package | Description |
|---------|---------|
|Éducation (étudiant de l’enseignement supérieur)    |Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux étudiants de l’enseignement supérieur.|
|Éducation (étudiant du primaire)   |Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux étudiants du primaire.|
|Éducation (étudiant de l’enseignement secondaire)    |Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux étudiants secondaires.         |
|Éducation (enseignant)    |Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux enseignants.      |
|Éducation (enseignant du primaire utilisant l’apprentissage à distance)    |Création d’un groupe de stratégies qui s’appliquent aux enseignants du primaire pour optimiser la sécurité et la collaboration des étudiants lors de l’utilisation de l’apprentissage à distance.      |
|Éducation (étudiant du primaire à l’aide de l’apprentissage à distance)    |Création d’un groupe de stratégies qui s’appliquent aux étudiants du primaire pour optimiser la sécurité et la collaboration des étudiants lors de l’utilisation de l’apprentissage à distance.      |
|Gestionnaire en ligne |Crée un ensemble de stratégies et applique ces paramètres aux responsables en ligne de votre organisation. |
|Employé en ligne |Crée un ensemble de stratégies et applique ces paramètres aux employés en ligne de votre organisation. |
|Professionnel de la santé  |Crée un ensemble de stratégies et de paramètres de stratégies qui offrent aux travailleurs cliniques tels que les infirmières autorisées, les infirmières responsables, les médecins et les travailleurs sociaux un accès complet à la conversation, aux appels, à la gestion des équipes et aux réunions. |
|Travailleurs de l’information sur le secteur de la santé  |Crée un ensemble de stratégies et de paramètres de stratégie qui donnent aux travailleurs de l’information, par exemple, le personnel de l’information, l’informatique, le personnel financier et les responsables de la mise en conformité, un accès total aux discussions, aux appels et aux réunions.|
|Salle de soins de santé  |Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux salles des patients dans votre organisation de santé.|
|Petite et moyenne entreprise (Business Voice) |Crée une stratégie de configuration d’application qui inclut les applications pour une expérience vocale professionnelle.|
|Petite et moyenne entreprise (sans Voix Entreprise) |Crée une stratégie de configuration d’application pertinente pour les petites et moyennes Teams d’utilisateurs (expérience vocale non professionnelle).
|Responsable de la sécurité publique   |Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux responsables de la sécurité publique de votre organisation.|

> [!NOTE]
> Nous ajouterons d’autres packages de stratégie dans les prochaines Teams, aussi consultez-nous à nouveau pour obtenir les informations les plus à jour.  

Chaque stratégie individuelle reçoit le nom du package de stratégie afin de vous permettre d’identifier facilement les stratégies liées à un package de stratégie.
Par exemple, lorsque vous affectez le package de stratégie Éducation (Enseignant) aux enseignants de votre établissement scolaire, une stratégie nommée Education_Teacher est créée pour chaque stratégie du package.

![Capture d’écran du package de stratégie Éducation (enseignant).](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a>Packages de stratégie personnalisée

Les packages de stratégies personnalisées vous offrent votre propre ensemble de stratégies pour les utilisateurs ayant des rôles similaires au sein de votre organisation. Créez vos propres packages de stratégies en ajoutant les types de stratégies et les stratégies dont vous avez besoin.

Pour créer un package de stratégie personnalisé :

1. Dans la barre de navigation gauche du Microsoft Teams d’administration, sélectionnez **Packages** de stratégie, puis cliquez sur **Ajouter.**

    :::image type="content" source="media/policy-packages-add.png" alt-text="Capture d’écran du bouton Ajouter dans la page Packages de stratégie du Centre d’administration.":::

2. Entrez un nom et une description pour votre package.

    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="Capture d’écran de l’ajout d’un nouveau package de stratégie personnalisée.":::

3. Sélectionnez les types de stratégies et les noms de stratégies à inclure dans le package.

4. Cliquez sur **Enregistrer**.

## <a name="how-to-use-policy-packages"></a>Comment utiliser des packages de stratégie

L’exemple suivant explique comment utiliser des packages de stratégie dans votre organisation.

![Vue d’ensemble de l’utilisation des packages de stratégie.](media/manage-policy-packages-overview.png)

- **[Affichage](#view-the-settings-of-a-policy-in-a-policy-package)**: afficher les stratégies dans un package de stratégie. Vous pouvez ensuite afficher les paramètres de chaque stratégie dans un package avant de l’affecter. Assurez-vous de comprendre chaque paramètre. Déterminez si les valeurs prédéfinies sont appropriées pour votre organisation ou si vous devez les modifier pour qu’elles soient plus restrictives ou moins restrictives en fonction des besoins de votre organisation.

    Si une stratégie est supprimée, vous pouvez toujours afficher les paramètres, mais vous ne pouvez pas modifier les paramètres. Une stratégie supprimée est re-créée avec les paramètres prédéfinés lorsque vous attribuez le package de stratégie.

- **[Personnaliser](#customize-policies-in-a-policy-package)**: personnalisez les paramètres des stratégies dans le package de stratégies pour répondre aux besoins de votre organisation.

- **[Attribuer :](#assign-a-policy-package)** affecter le package de stratégie aux utilisateurs.  

> [!NOTE]
> Vous pouvez également modifier les paramètres des stratégies dans un package de stratégie après avoir attribué un package. Les modifications que vous apportez aux paramètres de stratégie sont automatiquement appliquées aux utilisateurs auxquels le package est attribué.

Voici comment afficher, attribuer et personnaliser des packages de stratégie dans le Centre d’administration Microsoft Teams’administration.

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a>Afficher les paramètres d’une stratégie dans un package de stratégie

1. Dans le navigation gauche du Microsoft Teams d’administration, sélectionnez **Packages** de stratégie, puis sélectionnez un package de stratégie en cliquant à gauche du nom du package.

2. Cliquez sur la stratégie à afficher.

### <a name="customize-policies-in-a-policy-package"></a>Personnaliser les stratégies dans un package de stratégie

Vous pouvez modifier les paramètres d’une stratégie via la page **Packages** de stratégie ou en vous rendre directement sur la page stratégie dans le Microsoft Teams d’administration.

1. Dans le panneau de navigation gauche du Microsoft Teams d’administration, faites l’une des choses suivantes :
    - Cliquez **sur Packages de stratégie,** puis sélectionnez le package de stratégie en cliquant à gauche du nom du package.
    - Cliquez sur le type de stratégie.  Par exemple, cliquez sur **Stratégies de messagerie.**

2. Sélectionnez la stratégie à modifier. Les stratégies liées à un package de stratégies ont le même nom que le package de stratégies.

3. A apporter les modifications de votre souhaitez, puis cliquez sur **Enregistrer.**

### <a name="assign-a-policy-package"></a>Attribuer un package de stratégie

Vous pouvez affecter un package de stratégie à un utilisateur, un groupe ou un lot d’utilisateurs. Pour plus d’informations sur l’attribution de packages de stratégie, voir [Attribuer des packages de stratégie à des utilisateurs et groupes.](assign-policy-packages.md)

## <a name="related-topics"></a>Voir aussi

- [Attribuer des packages de stratégie](assign-policy-packages.md)
- [Teams packages de stratégie pour les administrateurs EDU](policy-packages-edu.md)
- [Packages de stratégie Teams pour la santé publique](policy-packages-healthcare.md)
- [Teams packages de stratégies pour le gouvernement](policy-packages-gov.md)
