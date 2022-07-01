---
title: Packages de stratégie Teams pour la santé publique
ms.author: mabond
author: mkbond007
manager: serdars
ms.reviewer: aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
ms.localizationpriority: medium
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Découvrez comment utiliser et gérer les packages de stratégies Teams pour votre organisation de santé publique.
ms.openlocfilehash: c4a1d6909cd6a2c7f58c3a30353a3d4398c4c70e
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/30/2022
ms.locfileid: "66563722"
---
# <a name="teams-policy-packages-for-healthcare"></a>Packages de stratégie Teams pour la santé publique

## <a name="overview"></a>Présentation

Un [package de stratégie](manage-policy-packages.md) dans Microsoft Teams est un ensemble de stratégies et de paramètres de stratégie prédéfinis que vous pouvez affecter aux utilisateurs ayant des rôles similaires dans votre organisation. Les packages de stratégie simplifient, rationalisent et garantissent la cohérence lors de la gestion des stratégies. Vous pouvez personnaliser les paramètres des stratégies dans le package en fonction des besoins de vos utilisateurs. Lorsque vous modifiez les paramètres des stratégies dans un package de stratégie, tous les utilisateurs qui sont affectés à ce package obtiennent les paramètres mis à jour. Vous pouvez gérer les packages de stratégie à l’aide du Centre d’administration Microsoft Teams ou de PowerShell.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Ht2o]

Les packages de stratégie pré-définissent les stratégies suivantes, selon le package :

- Messagerie
- Réunions
- Appel
- Configuration de l’application
- Événements en direct

Teams inclut actuellement les packages de stratégies de santé suivants.

|Nom du package dans le Centre d’administration Microsoft Teams|Idéal pour|Description |
|---------|---------|---------|
|Professionnel de la santé  |Professionnels de la santé de votre organisation de santé  |Crée un ensemble de stratégies et de paramètres de stratégies qui offrent aux travailleurs cliniques tels que les infirmières autorisées, les infirmières responsables, les médecins et les travailleurs sociaux un accès complet à la conversation, aux appels, à la gestion des équipes et aux réunions. |
|Travailleurs de l’information sur le secteur de la santé  |Travailleurs de l’information de votre organisation de santé |Crée un ensemble de stratégies et de paramètres de stratégie qui donnent aux travailleurs de l’information, par exemple, le personnel de l’information, l’informatique, le personnel financier et les responsables de la mise en conformité, un accès total aux discussions, aux appels et aux réunions.|
|Salle de soins de santé  |Appareils de salle des patients|Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux salles des patients dans votre organisation de santé.|

![Capture d’écran des packages de stratégie de santé.](media/policy-packages-healthcare.png)

Chaque stratégie individuelle reçoit le nom du package de stratégie afin de vous permettre d’identifier facilement les stratégies liées à un package de stratégie. Par exemple, lorsque vous affectez le package de stratégie des professionnels de la santé à des médecins de votre organisation, une stratégie nommée Healthcare_ClinicalWorker est créée pour chaque stratégie du package.

![Capture d’écran des politiques dans le package Healthcare Clinical Worker.](media/policy-packages-healthcare-clinical-worker.png)

## <a name="get-started-with-policy-packages"></a>Prise en main avec les packages de stratégie

Pour prendre en charge les packages de stratégies de santé, sur le hub d’intégration du Centre d’administration Microsoft, sélectionnez **Healthcare**, puis sélectionnez **Attribuer des paramètres de stratégie par rôle**. Lorsque vous êtes prêt à commencer, décidez des packages de stratégies à attribuer aux membres de votre organisation.

Sélectionnez **Afficher les détails de la stratégie** pour en savoir plus sur les stratégies spécifiques dans un package et leurs paramètres respectifs. Ces [peuvent être personnalisées](manage-policy-packages.md#customize-policies-in-a-policy-package) après un affectation dans le Centre d’administration Teams.

Choisissez un ou plusieurs packages à affecter, puis cliquez sur **Suivant**. Vous pouvez rechercher et ajouter des personnes au package de stratégie le mieux adapté à leur rôle. Une personne ne peut pas être affectée à plusieurs packages de stratégie à la fois.

Une fois que vous avez ajouté des personnes au package de stratégies de votre choix, **Terminer** finalise vos sélections. Vous pouvez continuer à personnaliser et à gérer les packages de stratégie dans le Centre d’administration Microsoft Teams.

## <a name="manage-policy-packages"></a>Gérer vos packages de stratégie

### <a name="view"></a>Afficher

Afficher les paramètres de chaque stratégie dans un package de stratégie avant d’attribuer un package. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez **Packages de stratégie**, sélectionnez le nom du package, puis sélectionnez le nom de la stratégie.

Déterminez si les valeurs prédéfinies conviennent à votre organisation ou si vous devez les personnaliser pour les rendre plus restrictives ou plus strictes en fonction des besoins de votre organisation.

### <a name="customize"></a>Personnaliser

Personnalisez les paramètres des stratégies dans le package de stratégie, le cas échéant, pour répondre aux besoins de votre organisation. Les modifications que vous apportez aux paramètres de stratégie sont automatiquement appliquées aux utilisateurs auxquels le package est attribué. Pour modifier les paramètres d’une stratégie dans un package de stratégie, dans le navigation gauche du Centre d’administration Microsoft Teams, accédez à **Packages de stratégie**, sélectionnez le package de stratégie, sélectionnez le nom de la stratégie que vous voulez modifier, puis sélectionnez **Modifier**.

Gardez à l’esprit que vous pouvez également modifier les paramètres des stratégies dans un package une fois que vous avez affecté le package de stratégie. Pour plus d’informations, consultez [Personnaliser des stratégies dans un package de stratégie](manage-policy-packages.md#customize-policies-in-a-policy-package).

### <a name="assign"></a>Attribuer

Affecter un package de stratégie à des utilisateurs. Si une stratégie est attribuée à un utilisateur et que vous affectez une autre stratégie plus tard, l’affectation la plus récente prend la priorité.

> [!NOTE]
> Chaque utilisateur aura besoin du module complémentaire Communications avancées pour recevoir une attribution de package de stratégie personnalisée. Pour plus d’informations, consultez [Module complémentaire Communications avancées pour Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).

#### <a name="assign-a-policy-package-to-one-or-several-users"></a>Attribuer un package de stratégie à un ou plusieurs utilisateurs

Pour attribuer un package de stratégie à un ou plusieurs utilisateurs, dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez à **Packages de stratégie**, puis sélectionnez **Gérer les utilisateurs**.  

![Capture d’écran de l’attribution d’un package de stratégie dans le Centre d’administration.](media/policy-packages-healthcare-assign.png)

Pour plus d’informations, consultez la section [Attribuer un package de stratégie](assign-policy-packages.md).

Si une stratégie est attribuée à un utilisateur et que vous affectez une autre stratégie plus tard, l’affectation la plus récente prend la priorité.

#### <a name="assign-a-policy-package-to-a-group"></a>Attribuer le package stratégie à un groupe

**Cette fonctionnalité est en mode privé (préversion)**

Attribution de package de stratégie aux groupes vous permet d’attribuer plusieurs stratégies à un groupe d’utilisateurs, tel qu’un groupe de sécurité ou une liste de distribution. L’affectations de stratégie est propagée aux membres du groupe en fonction de règles de priorité. Lorsque les membres sont ajoutés à un groupe ou supprimés de ceux-ci, leurs affectations de stratégie héritées sont mises à jour en conséquence. Cette méthode est recommandée pour les groupes disposant jusqu’à 50 000 utilisateurs, mais aussi pour les groupes de plus grande taille.

Pour plus d’informations, consultez la section [Attribuer un package de stratégie à un groupe](assign-policy-packages.md#assign-a-policy-package-to-a-group).

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a>Attribuer un package de stratégie à un grand ensemble (lot) d’utilisateurs

Utilisez l’attribution de package de stratégie de traitement par lots pour attribuer un package de stratégie à d’importants ensembles d’utilisateurs à la fois. L’applet de commande [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) vous permet de soumettre un lot d’utilisateurs et le package de stratégie que vous voulez attribuer. Les attributions sont traitées comme une opération d’arrière-plan et un ID d’opération est généré pour chaque lot.

Un lot peut contenir jusqu’à 5 000 utilisateurs. Vous pouvez spécifier des utilisateurs à l’aide de leur ID d’objet, de leur nom d’utilisateur, de leur adresse SIP ou de leur adresse de courrier. Pour plus d’informations, consultez la section [Attribuer un package de stratégie à un lot d’utilisateurs](assign-policy-packages.md#assign-a-policy-package-to-a-batch-of-users).

## <a name="related-topics"></a>Rubriques connexes

[Gérer les packages de stratégie dans Teams](manage-policy-packages.md)

[Affecter des packages de stratégie à des utilisateurs et des groupes](assign-policy-packages.md)
