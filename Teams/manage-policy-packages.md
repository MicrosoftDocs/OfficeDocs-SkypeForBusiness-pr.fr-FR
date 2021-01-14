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
description: Découvrez comment utiliser et gérer des packages de stratégies dans Microsoft Teams pour simplifier, rationaliser et offrir une cohérence dans le cadre de la gestion des stratégies pour des groupes d’utilisateurs.
ms.openlocfilehash: 9718751ea1d34692718b63cbe90ee6e694577c21
ms.sourcegitcommit: c537b1cf03e7ac5d07f2fbf4ba73d73c510f3d96
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49862585"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a>Gérer les packages de stratégie dans Microsoft Teams

> [!NOTE]
> Une des fonctionnalités abordées dans cet article, les packages de stratégie [personnalisée,](#custom-policy-packages)est actuellement en prévisualisation privée.

Un package de stratégie dans Microsoft Teams est un ensemble de stratégies et de paramètres de stratégie prédéfinés que vous pouvez affecter aux utilisateurs ayant des rôles similaires dans votre organisation. Nous avons créé des packages de stratégies pour simplifier, rationaliser et offrir une cohérence dans le cadre de la gestion des stratégies pour des groupes d’utilisateurs au sein de votre organisation.  

Vous pouvez utiliser les [packages de stratégie inclus dans Teams](#policy-packages-included-in-teams) ou créer vos propres packages de stratégie [personnalisés](#custom-policy-packages) (en prévisualisation privée).

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="Capture d’écran de la page Packages de stratégie dans le Centre d’administration":::

Vous pouvez personnaliser les paramètres des stratégies dans un package de stratégies pour répondre aux besoins de vos utilisateurs. Lorsque vous modifiez les paramètres des stratégies dans un package, tous les utilisateurs affectés à ce package obtiennent les paramètres mis à jour. Vous gérez les packages de stratégie à l’aide du Centre d’administration Microsoft Teams ou de PowerShell.

## <a name="what-is-a-policy-package"></a>Qu’est-ce qu’un package de stratégie ?

Les packages de stratégie vous permettent de contrôler les fonctionnalités Teams que vous voulez autoriser ou restreindre pour des ensembles spécifiques de personnes au sein de votre organisation. Chaque package de stratégie dans Teams est conçu autour d’un rôle d’utilisateur et inclut des stratégies et paramètres de stratégie prédéfinés qui supportent les activités de collaboration et de communication classiques pour ce rôle.

Les packages de stratégies prisent en charge les types de stratégies Teams suivants :

- Stratégie de messagerie
- Stratégie de réunion
- Stratégie de configuration de l’application
- Stratégie d’Appel
- Stratégie d’événements en direct

## <a name="policy-packages-included-in-teams"></a>Packages de stratégie inclus dans Teams

Teams inclut actuellement les packages de stratégie suivants.

|**Nom du package**  |**Description** |
|---------|---------|
|Éducation (étudiant de l’enseignement supérieur)    |Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux étudiants de l’enseignement supérieur.|
|Éducation (étudiant du primaire)   |Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux étudiants du primaire.|
|Éducation (étudiant de l’enseignement secondaire)    |Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux étudiants secondaires.         |
|Éducation (enseignant)    |Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux enseignants.      |
|Éducation (enseignant du primaire utilisant l’apprentissage à distance)    |Création d’un groupe de stratégies qui s’appliquent aux enseignants du primaire pour optimiser la sécurité et la collaboration des étudiants lors de l’utilisation de l’apprentissage à distance.      |
|Éducation (étudiant du primaire à l’aide de l’apprentissage à distance)    |Création d’un groupe de stratégies qui s’appliquent aux étudiants du primaire pour optimiser la sécurité et la collaboration des étudiants lors de l’utilisation de l’apprentissage à distance.      |
|Gestionnaire en ligne |Crée un ensemble de stratégies et applique ces paramètres aux responsables fronttline de votre organisation. |
|Employé de fronttline |Crée un ensemble de stratégies et applique ces paramètres aux employés de fronttline de votre organisation. |
|Travailleur clinique de santé  |Crée un ensemble de stratégies et de paramètres de stratégie qui donnent aux travailleurs cliniques, comme des infirmières inscrites, des infirmières et des travailleurs sociaux un accès complet aux discussions, aux appels, à la gestion des shifts et aux réunions. |
|Travailleur de l’information sur les soins de santé  |Crée un ensemble de stratégies et de paramètres de stratégies qui donnent aux travailleurs de l’information, tels que le personnel de l’information, le personnel en informatique, le personnel financier et les responsables de la mise en conformité, un accès total aux discussions, aux appels et aux réunions.|
|Salle de soins de santé  |Crée un ensemble de stratégies et de paramètres de stratégies qui s’appliquent aux salles des patients de votre organisation de soins de santé.|
|Petite et moyenne entreprise (Business Voice) |Crée une stratégie de configuration d’application qui inclut les applications pour une expérience vocale professionnelle.|
|Petite et moyenne entreprise (sans Voix Entreprise) |Crée une stratégie de configuration d’application pertinente pour les utilisateurs Teams de petite et moyenne entreprise (expérience autre que Voix Entreprise).
|Responsable de la sécurité publique   |Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux responsables de la sécurité publique de votre organisation.|

> [!NOTE]
> Nous ajouterons d’autres packages de stratégie dans les prochaines publication de Teams. Consultez à nouveau les informations les plus à jour.  

Le nom du package de stratégies est donné à chaque stratégie individuelle, ce qui vous permet d’identifier facilement les stratégies liées à un package de stratégie.
Par exemple, lorsque vous affectez le package de stratégie Éducation (Enseignant) aux enseignants de votre établissement scolaire, une stratégie nommée Education_Teacher est créée pour chaque stratégie du package.

![Capture d’écran du package de stratégie Éducation (enseignant)](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a>Packages de stratégie personnalisée

**Cette fonctionnalité est en mode privé (préversion)**

Les packages de stratégies personnalisées vous offrent votre propre ensemble de stratégies pour les utilisateurs ayant des rôles similaires dans votre organisation. Créez vos propres packages de stratégies en ajoutant les types de stratégies et les stratégies dont vous avez besoin.

Pour créer un package de stratégie personnalisé :

1. Dans le panneau de navigation gauche du Centre d’administration Microsoft Teams, sélectionnez **Packages** de stratégie, puis cliquez sur **Ajouter.**
    :::image type="content" source="media/policy-packages-add.png" alt-text="Capture d’écran du bouton Ajouter dans la page Packages de stratégie du Centre d’administration":::
2. Entrez un nom et une description pour votre package.
    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="Capture d’écran de l’ajout d’un nouveau package de stratégie personnalisée":::
3. Sélectionnez les types de stratégies et les noms de stratégies à inclure dans le package.
4. Cliquez sur **Enregistrer**.

## <a name="how-to-use-policy-packages"></a>Comment utiliser des packages de stratégie

L’exemple suivant explique comment utiliser des packages de stratégie dans votre organisation.

![Vue d’ensemble de l’utilisation des packages de stratégie](media/manage-policy-packages-overview.png)

- **[Affichage](#view-the-settings-of-a-policy-in-a-policy-package)**: afficher les stratégies dans un package de stratégie. Vous pouvez ensuite afficher les paramètres de chaque stratégie dans un package avant de l’affecter. Assurez-vous de comprendre chaque paramètre. Déterminez si les valeurs prédéfinies sont appropriées pour votre organisation ou si vous devez les modifier pour qu’elles soient plus restrictives ou moins restrictives en fonction des besoins de votre organisation.

    Si une stratégie est supprimée, vous pouvez toujours afficher les paramètres, mais vous ne pouvez pas modifier les paramètres. Une stratégie supprimée est re-créée avec les paramètres prédéfinés lorsque vous affectez le package de stratégie.

- **[Personnaliser](#customize-policies-in-a-policy-package)**: personnalisez les paramètres des stratégies dans le package de stratégies pour répondre aux besoins de votre organisation.

- **[Attribuer :](#assign-a-policy-package)** affecter le package de stratégie aux utilisateurs.  

> [!NOTE]
> Vous pouvez également modifier les paramètres des stratégies dans un package de stratégie après avoir attribué un package. Les modifications que vous apportez aux paramètres de stratégie sont automatiquement appliquées aux utilisateurs auxquels le package est attribué.

Voici comment afficher, attribuer et personnaliser des packages de stratégie dans le Centre d’administration Microsoft Teams.

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a>Afficher les paramètres d’une stratégie dans un package de stratégie

1. Dans la navigation gauche du Centre d’administration Microsoft Teams, sélectionnez **Packages** de stratégie, puis sélectionnez un package de stratégie en cliquant à gauche du nom du package.
2. Cliquez sur la stratégie à afficher.

### <a name="customize-policies-in-a-policy-package"></a>Personnaliser les stratégies dans un package de stratégie

Vous pouvez modifier les paramètres d’une stratégie via la page **packages** de stratégie ou en vous rendre directement sur la page stratégie dans le Centre d’administration Microsoft Teams.

1. Dans le panneau de navigation gauche du Centre d’administration Microsoft Teams, faites l’une des choses suivantes :
    - Cliquez **sur Packages de stratégie,** puis sélectionnez le package de stratégie en cliquant à gauche du nom du package.
    - Cliquez sur le type de stratégie.  Par exemple, cliquez **sur Stratégies de messagerie.**
2. Sélectionnez la stratégie à modifier. Les stratégies liées à un package de stratégies ont le même nom que le package de stratégies.
3. A apporter les modifications de votre souhaitez, puis cliquez sur **Enregistrer.**

### <a name="assign-a-policy-package"></a>Attribuer un package de stratégie 

#### <a name="assign-a-policy-package-to-one-user"></a>Attribuer un package de stratégie à un utilisateur

1. Dans le volet de navigation gauche du centre d’administration Microsoft Teams, et accédez aux **Utilisateurs**, puis cliquez sur l’utilisateur.
2. Dans la page de l’utilisateur, cliquez sur **Stratégies,** puis, à côté de **Package** de stratégie, cliquez sur **Modifier.**
3. Dans le **volet Attribuer un package** de stratégie, sélectionnez le package à attribuer, puis cliquez sur **Enregistrer.**

#### <a name="assign-a-policy-package-to-multiple-users"></a>Attribuer un package de stratégie à plusieurs utilisateurs

1. Dans la navigation gauche du Centre d’administration Microsoft Teams, sélectionnez **Packages** de stratégie, puis sélectionnez le package de stratégie à attribuer en cliquant à gauche du nom du package.
2. Cliquez sur **Gérer les utilisateurs.**
3. Dans le volet **Gérer les utilisateurs**, recherchez l’utilisateur par son nom complet ou son nom d’utilisateur, sélectionnez le nom, puis cliquez sur **Ajouter**. Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.
4. Lorsque vous avez terminé d’ajouter des utilisateurs, cliquez sur **Enregistrer.**

#### <a name="assign-a-policy-package-to-a-group"></a>Attribuer le package stratégie à un groupe

**Cette fonctionnalité est en mode privé (préversion)**

Attribution de package de stratégie aux groupes vous permet d’attribuer plusieurs stratégies à un groupe d’utilisateurs, tel qu’un groupe de sécurité ou une liste de distribution. L’affectations de stratégie est propagée aux membres du groupe en fonction de règles de priorité. Lorsque les membres sont ajoutés à un groupe ou supprimés de ceux-ci, leurs affectations de stratégie héritées sont mises à jour en conséquence. Cette méthode est recommandée pour les groupes disposant jusqu’à 50 000 utilisateurs, mais aussi pour les groupes de plus grande taille.

Pour plus d’informations, consultez la section [Attribuer un package de stratégie à un groupe](assign-policies.md#assign-a-policy-package-to-a-group).

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a>Attribuer un package de stratégie à un grand ensemble (lot) d’utilisateurs

Utilisez l’attribution de package de stratégie de traitement par lots pour attribuer un package de stratégie à d’importants ensembles d’utilisateurs à la fois. L’applet de commande [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) vous permet de soumettre un lot d’utilisateurs et le package de stratégie que vous voulez attribuer. Les attributions sont traitées comme une opération d’arrière-plan et un ID d’opération est généré pour chaque lot.

Un lot peut contenir jusqu’à 5 000 utilisateurs. Vous pouvez spécifier des utilisateurs à l’aide de leur ID d’objet, de leur nom d’utilisateur, de leur adresse SIP ou de leur adresse de courrier. Pour plus d’informations, consultez la section [Attribuer un package de stratégie à un lot d’utilisateurs](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).

## <a name="troubleshooting"></a>Résolution des problèmes

**Vous recevez une erreur lorsque vous affectez un package de stratégie**

Cela peut se produire si une ou plusieurs stratégies du package n’ont pas été créées ou appliquées correctement. Réattribuez le package de stratégie à vos utilisateurs. Une nouvelle tentative d’opération résout généralement ce problème.

## <a name="related-topics"></a>Sujets associés

[Attribuer des stratégies à vos utilisateurs](assign-policies.md)

[Packages de stratégie Teams pour les administrateurs EDU](policy-packages-edu.md)

[Packages de stratégie Teams pour les soins de santé](policy-packages-healthcare.md)

[Packages de stratégie Teams pour le gouvernement](policy-packages-gov.md)
