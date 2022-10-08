---
title: Packages de stratégie Teams pour les travailleurs de première ligne
ms.author: v-lanachin
author: LanaChin
manager: samanro
ms.reviewer: ''
ms.topic: article
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
f1.keywords: ''
ms.custom: ''
ms.localizationpriority: high
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft 365 for frontline workers
description: Découvrez comment utiliser et gérer les packages de stratégies Teams pour les travailleurs de première ligne de votre organisation.
ms.openlocfilehash: 62a3d047da0f9174bc26d5a1e9c3ebe5f9467a49
ms.sourcegitcommit: 507e186972bcbc56c1547a1b9f357bfd38170b5a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68047194"
---
# <a name="teams-policy-packages-for-frontline-workers"></a>Packages de stratégie Teams pour les travailleurs de première ligne

## <a name="overview"></a>Présentation

Un [package de stratégie](manage-policy-packages.md) dans Microsoft Teams est un ensemble de stratégies et de paramètres de stratégie prédéfinis que vous pouvez affecter aux utilisateurs ayant des rôles similaires dans votre organisation. Les packages de stratégie simplifient, rationalisent et garantissent la cohérence lors de la gestion des stratégies.

Vous pouvez personnaliser les paramètres des stratégies dans le package en fonction des besoins de vos utilisateurs. Lorsque vous modifiez les paramètres des stratégies dans un package de stratégie, tous les utilisateurs qui sont affectés à ce package obtiennent les paramètres mis à jour. Vous pouvez gérer les packages de stratégie à l’aide du Centre d’administration Microsoft Teams ou de PowerShell.

Les packages de stratégie pré-définissent les stratégies suivantes, selon le package :

- Messagerie
- Réunions
- Appel
- Configuration de l’application
- Événements en direct

Teams inclut les packages de stratégie **Gestionnaire de première ligne** et **Travailleur de première ligne** .

|Nom du package dans le Centre d’administration Microsoft Teams|Description |
|---------|---------|
|**Gestionnaire de première ligne** |Crée un ensemble de stratégies et applique ces paramètres aux responsables de première ligne de votre organisation. |
|**Travailleur de première ligne**  |Crée un ensemble de stratégies et applique ces paramètres aux travailleurs de première ligne de votre organisation.|

:::image type="content" source="media/policy-packages-flw.png" alt-text="Capture d’écran des packages de stratégie de première ligne." lightbox="media/policy-packages-flw.png":::

Chaque stratégie individuelle reçoit le nom du package de stratégie afin de vous permettre d’identifier facilement les stratégies liées à un package de stratégie. Par exemple, lorsque vous affectez le package de Gestionnaire de première ligne à des responsables de magasin de votre organisation, une stratégie nommée Frontline_Manager est créée pour chaque stratégie du package.

:::image type="content" source="media/policy-packages-flw-frontline-manager.png" alt-text="Capture d’écran des stratégies dans le package de stratégie du Gestionnaire de première ligne." lightbox="media/policy-packages-flw-frontline-manager.png":::

## <a name="manage-policy-packages"></a>Gérer vos packages de stratégie

### <a name="view"></a>Afficher

Afficher les paramètres de chaque stratégie dans un package de stratégie avant d’attribuer un package. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez **Packages de stratégie**, sélectionnez le nom du package, puis sélectionnez le nom de la stratégie.

Déterminez si les valeurs prédéfinies conviennent à votre organisation ou si vous devez les personnaliser pour les rendre plus restrictives ou plus strictes en fonction des besoins de votre organisation.

### <a name="customize"></a>Personnaliser

Personnalisez les paramètres des stratégies dans le package de stratégie, le cas échéant, pour répondre aux besoins de votre organisation. Les modifications que vous apportez aux paramètres de stratégie sont automatiquement appliquées aux utilisateurs auxquels le package est attribué. Pour modifier les paramètres d’une stratégie dans un package de stratégie, dans le navigation gauche du Centre d’administration Microsoft Teams, accédez à **Packages de stratégie**, sélectionnez le package de stratégie, sélectionnez le nom de la stratégie que vous voulez modifier, puis sélectionnez **Modifier**.

Gardez à l’esprit que vous pouvez également modifier les paramètres des stratégies dans un package une fois que vous avez affecté le package de stratégie. Pour plus d’informations, consultez [Personnaliser des stratégies dans un package de stratégie](manage-policy-packages.md#customize-policies-in-a-policy-package).

### <a name="assign"></a>Attribuer

Assign the policy package to users. If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.

> [!NOTE]
> Chaque utilisateur aura besoin du module complémentaire Communications avancées pour recevoir une attribution de package de stratégie personnalisée. Pour plus d’informations, consultez [Module complémentaire Communications avancées pour Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).

#### <a name="assign-a-policy-package-to-one-or-several-users"></a>Attribuer un package de stratégie à un ou plusieurs utilisateurs

Pour attribuer un package de stratégie à un ou plusieurs utilisateurs, dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez à **Packages de stratégie**, puis sélectionnez **Gérer les utilisateurs**.  

:::image type="content" source="media/policy-packages-flw-frontline-manager-assign.png" alt-text="Capture d’écran de l’attribution d’un package de stratégie à un utilisateur dans le Centre d’administration Teams." lightbox="media/policy-packages-flw-frontline-manager-assign.png":::

Pour plus d’informations, consultez [Attribuer des packages de stratégie à des utilisateurs](assign-policy-packages.md#assign-a-policy-package-to-users).

#### <a name="assign-a-policy-package-to-a-group"></a>Attribuer le package stratégie à un groupe

L’attribution de package de stratégie à des groupes vous permet d’affecter plusieurs stratégies à un groupe d’utilisateurs, comme un groupe de sécurité ou une liste de distribution. L’affectations de stratégie est propagée aux membres du groupe en fonction de règles de priorité. Lorsque les membres sont ajoutés à un groupe ou supprimés de ceux-ci, leurs affectations de stratégie héritées sont mises à jour en conséquence. Cette méthode est recommandée pour les groupes disposant jusqu’à 50 000 utilisateurs, mais aussi pour les groupes de plus grande taille.

Pour plus d’informations, consultez la section [Attribuer un package de stratégie à un groupe](assign-policy-packages.md#assign-a-policy-package-to-a-group).

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a>Attribuer un package de stratégie à un grand ensemble (lot) d’utilisateurs

Utilisez l’attribution de package de stratégie de traitement par lots pour attribuer un package de stratégie à d’importants ensembles d’utilisateurs à la fois. L’applet de commande [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) vous permet de soumettre un lot d’utilisateurs et le package de stratégie que vous voulez attribuer. Les attributions sont traitées comme une opération d’arrière-plan et un ID d’opération est généré pour chaque lot.

Un lot peut contenir jusqu’à 5 000 utilisateurs. Vous pouvez spécifier des utilisateurs par leur ID d’objet ou leur adresse SIP (Session Initiation Protocol). Pour plus d’informations, consultez la section [Attribuer un package de stratégie à un lot d’utilisateurs](assign-policy-packages.md#assign-a-policy-package-to-a-batch-of-users).

## <a name="related-topics"></a>Rubriques connexes

- [Gérer les packages de stratégie dans Teams](manage-policy-packages.md)
- [Affecter des packages de stratégie à des utilisateurs et des groupes](assign-policy-packages.md)
