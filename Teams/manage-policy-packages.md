---
title: Gérer les packages de stratégie dans Microsoft teams
author: lanachin
ms.author: v-lanac
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
description: Découvrez comment utiliser et gérer des packages de stratégie dans Microsoft teams pour simplifier, simplifier et garantir la cohérence lors de la gestion des stratégies pour les groupes d’utilisateurs.
ms.openlocfilehash: 62151d9356e414f0f527e597492be685c0067fd0
ms.sourcegitcommit: 86b0956680b867b8bedb2e969220b8006829ee53
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/28/2020
ms.locfileid: "44412531"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a>Gérer les packages de stratégie dans Microsoft teams

Un package de stratégie dans Microsoft teams est un ensemble de stratégies et de paramètres de stratégie prédéfinis que vous pouvez affecter aux utilisateurs ayant des rôles similaires au sein de votre organisation. Nous avons conçu des packages de stratégie pour simplifier, rationaliser et garantir la cohérence lors de la gestion des stratégies pour les groupes d’utilisateurs au sein de votre organisation.  

Lorsque vous attribuez un package de stratégie aux utilisateurs, les stratégies du package sont créées et vous pouvez personnaliser les paramètres des stratégies du package en fonction des besoins de votre organisation.

Les packages de stratégie ne sont pas disponibles pour les organisations américaines de la communauté Cloud.

## <a name="what-is-a-policy-package"></a>Qu’est-ce qu’un package de stratégie ?

Les packages de stratégie vous permettent de contrôler les fonctionnalités d’équipes que vous souhaitez autoriser ou restreindre pour des ensembles de personnes spécifiques au sein de votre organisation. Chaque package de stratégie dans teams est conçu en fonction d’un rôle d’utilisateur et comprend des stratégies et des paramètres de stratégie prédéfinis qui prennent en charge les activités de collaboration et de communication qui sont les plus typiques pour ce rôle.

Teams inclut actuellement les packages de stratégie suivants.

|**Nom du package**  |**Description** |
|---------|---------|
|Éducation (étudiant de grande éducation)    |Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux étudiants de plus grande éducation.|
|Éducation (étudiant primaire)   |Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux étudiants principaux.|
|Éducation (étudiant d’école secondaire)    |Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux étudiants secondaires.         |
|Éducation (enseignant)    |Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux enseignants.      |
|Éducation (Université principal d’école à distance)    |Création d’un groupe de stratégies qui s’appliquent aux enseignants du primaire pour optimiser la sécurité et la collaboration des étudiants lors de l’utilisation de l’apprentissage à distance.      |
|Éducation (étudiant principal pour les établissements d’enseignement à distance)    |Création d’un groupe de stratégies qui s’appliquent aux étudiants du primaire pour optimiser la sécurité et la collaboration des étudiants lors de l’utilisation de l’apprentissage à distance.      |
|Travailleurs cliniques médicaux  |Crée un ensemble de stratégies et de paramètres de stratégie qui permettent aux travailleurs cliniques tels que les infirmières, les infirmières, les médecins et les travailleurs sociaux d’avoir un accès complet aux discussions, aux appels, à la gestion des équipes et aux réunions. |
|Travailleurs de l’information sur la santé  |Crée un ensemble de stratégies et de paramètres de stratégie qui permettent aux travailleurs de l’information, tels que le personnel informatique, le personnel informatique, le personnel financier et les responsables de la mise en conformité, un accès complet aux discussions, aux appels et aux réunions.|
|Salle de santé du patient  |Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux salles de soins de votre organisation.|
|Utilisateurs petites et moyennes entreprises (voix entreprise) |Crée une stratégie de configuration d’application qui inclut les applications pour une interface vocale professionnelle.|
|Utilisateurs petites et moyennes entreprises (sans voix entreprise) |Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux utilisateurs professionnels de petites et moyennes tailles sans fonctions vocales métiers.|
|Officier de sûreté public   |Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux responsables de la sécurité publique au sein de votre organisation.|



> [!NOTE]
> Comme nous allons ajouter d’autres packages de stratégie dans les futures versions de teams, vous pouvez consulter les informations les plus récentes.  

Chaque stratégie individuelle dispose du nom du package de stratégie, ce qui vous permet d’identifier facilement les stratégies liées à un package de stratégie.
Par exemple, lorsque vous attribuez le package de stratégie éducation (enseignant) aux enseignants de votre établissement scolaire, une stratégie nommée Education_Teacher est créée pour chaque stratégie dans le package.

![Capture d’écran du package de stratégie éducation (enseignant)](media/policy-packages-education_teacher.png)

## <a name="how-to-use-policy-packages"></a>Utiliser des packages de stratégie

Les plans suivants vous expliquent comment utiliser des packages de stratégie dans votre organisation.

![Vue d’ensemble de l’utilisation des packages de stratégie](media/manage-policy-packages-overview.png)

- **[Affichage](#view-the-settings-of-a-policy-in-a-policy-package)**: Affichez les paramètres de chaque stratégie d’un package de stratégie avant d’assigner un package. Vérifiez que vous comprenez chaque paramètre et déterminez si les valeurs prédéfinies conviennent à votre organisation, ou si vous devez les modifier de manière à ce qu’elles soient plus restrictives ou strictes en fonction des besoins de votre organisation.

    Si une stratégie est supprimée, vous pouvez toujours afficher les paramètres, mais vous ne pourrez pas modifier les paramètres. Une stratégie supprimée est à nouveau créée à l’aide des paramètres prédéfinis lorsque vous attribuez le package de stratégie.

- **[Attribuer](#assign-a-policy-package)**: attribuez le package de stratégie aux utilisateurs. N’oubliez pas que les stratégies d’un package de stratégie ne sont pas créées tant que vous n’avez pas affecté le package, vous pouvez modifier les paramètres des stratégies individuelles du package.  

- **[Personnaliser](#customize-policies-in-a-policy-package)**: Personnalisez les paramètres des stratégies dans le package de stratégie pour répondre aux besoins de votre organisation. Les modifications que vous apportez aux paramètres de stratégie s’appliquent automatiquement aux utilisateurs qui ont reçu le package.

Voici les étapes à suivre pour afficher, attribuer et personnaliser des packages de stratégie dans le centre d’administration Microsoft Teams.

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a>Afficher les paramètres d’une stratégie dans un package de stratégie

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, cliquez sur **packages de stratégie**, puis sélectionnez un package de stratégie en cliquant à gauche du nom du package.
2. Cliquez sur la stratégie que vous voulez afficher.

### <a name="assign-a-policy-package"></a>Assigner un package de stratégie

#### <a name="assign-a-policy-package-to-one-user"></a>Assigner un package de stratégie à un utilisateur

1. Dans le volet de navigation gauche du centre d’administration Microsoft Teams, et accédez aux **Utilisateurs**, puis cliquez sur l’utilisateur.
2. Sur la page de l’utilisateur, cliquez sur **stratégies**, puis en regard de **package de stratégie**, cliquez sur **modifier**.
3. Dans le volet **affecter un package de stratégie** , sélectionnez le package que vous voulez attribuer, puis cliquez sur **Enregistrer**.

#### <a name="assign-a-policy-package-to-multiple-users"></a>Assigner un package de stratégie à plusieurs utilisateurs

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **packages de stratégie**, puis sélectionnez le package de stratégie que vous voulez affecter en cliquant à gauche du nom du package.
2. Cliquez sur **gérer les utilisateurs**.
3. Dans le volet **Gérer les utilisateurs**, recherchez l’utilisateur par son nom complet ou son nom d’utilisateur, sélectionnez le nom, puis cliquez sur **Ajouter**. Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.
4. Lorsque vous avez terminé d’ajouter des utilisateurs, cliquez sur **Enregistrer**.

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a>Assigner un package de stratégie à un grand jeu (lot) d’utilisateurs

Utilisez une affectation de package de stratégie de lot pour assigner un package de stratégie à un grand nombre d’utilisateurs à la fois. Vous utilisez l’applet de commande [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) pour transmettre un lot d’utilisateurs et le package de stratégie que vous voulez affecter. Les affectations sont traitées en tant qu’opérations en arrière-plan et chaque lot est généré.

Un lot peut contenir jusqu’à 5 000 utilisateurs. Vous pouvez spécifier des utilisateurs en fonction de leur ID d’objet, de leur nom d’utilisateur principal, de leur adresse SIP ou de leur adresse de messagerie. Pour en savoir plus, voir [affecter un package de stratégie à un lot d’utilisateurs](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).

### <a name="customize-policies-in-a-policy-package"></a>Personnaliser les stratégies dans un package de stratégie

Vous pouvez modifier les paramètres d’une stratégie par le biais de la page **packages de stratégie** ou en accédant directement à la page de stratégie dans le centre d’administration Microsoft Teams.

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, effectuez l’une des opérations suivantes :
    - Cliquez sur **packages de stratégie**, puis sélectionnez le package de stratégie en cliquant à gauche du nom du package.
    - Cliquez sur le type de stratégie.  Par exemple, cliquez sur **stratégies de messagerie**.
2. Cliquez sur la stratégie que vous voulez modifier. Les stratégies liées à un package de stratégie portent le même nom que le package de stratégie.
3. Apportez les modifications souhaitées, puis cliquez sur **Enregistrer**.

## <a name="troubleshooting"></a>Résolution des problèmes

**Vous recevez un message d’erreur lorsque vous attribuez un package de stratégie**

Cela risque de se produire si une ou plusieurs stratégies du package n’ont pas été créées ou appliquées. Réattribuez-le à vos utilisateurs. Le renouvellement de l’opération résout généralement ce problème.

## <a name="related-topics"></a>Voir aussi

[Packages de stratégie Microsoft Teams pour les administrateurs dans l’éducation](policy-packages-edu.md)
