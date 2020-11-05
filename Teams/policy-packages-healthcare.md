---
title: Packages de stratégie d’équipe pour la santé
author: lanachin
ms.author: v-lanac
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
localization_priority: Normal
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Découvrez comment utiliser et gérer des packages de stratégie d’équipe pour votre organisation de santé.
ms.openlocfilehash: b8317a7f860d0ab8510a6170b69a50f7a3387ebd
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908513"
---
# <a name="teams-policy-packages-for-healthcare"></a>Packages de stratégie d’équipe pour la santé

## <a name="overview"></a>Vue d’ensemble

Un [package de stratégie](manage-policy-packages.md) dans Microsoft teams est un ensemble de stratégies et de paramètres de stratégie prédéfinis que vous pouvez affecter aux utilisateurs ayant des rôles similaires au sein de votre organisation. Les packages de stratégie simplifient, rationalisent et garantissent la cohérence lors de la gestion des stratégies. Vous pouvez personnaliser les paramètres des stratégies du package selon les besoins de vos utilisateurs. Lorsque vous modifiez les paramètres des stratégies dans un package de stratégie, tous les utilisateurs assignés à ce package obtiennent les paramètres mis à jour. Vous pouvez gérer des packages de stratégie à l’aide du centre d’administration Microsoft teams ou de PowerShell.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Ht2o]

Les packages de stratégie prédéfinis pour les éléments suivants, en fonction du package :

- Messagerie
- Réunions
- Appel
- Configuration de l’application
- Événements en direct

Teams inclut actuellement les packages de politique de santé suivants.

|Nom du package dans le centre d’administration Microsoft teams|Idéal pour|Description |
|---------|---------|---------|
|Travailleurs cliniques médicaux  |Travailleurs cliniques de votre organisation de santé  |Crée un ensemble de stratégies et de paramètres de stratégie qui permettent aux travailleurs cliniques tels que les infirmières, les infirmières, les médecins et les travailleurs sociaux d’avoir un accès complet aux discussions, aux appels, à la gestion des équipes et aux réunions. |
|Travailleurs de l’information sur la santé  |Travailleurs de l’information au sein de votre organisation de santé |Crée un ensemble de stratégies et de paramètres de stratégie qui permettent aux travailleurs de l’information, tels que le personnel informatique, le personnel informatique, le personnel financier et les responsables de la mise en conformité, un accès complet aux discussions, aux appels et aux réunions.|
|Salle de santé du patient  |Appareils de salle de patient|Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux salles de soins de votre organisation.|

![Capture d’écran des packages de politique de santé](media/policy-packages-healthcare.png)

Chaque stratégie individuelle dispose du nom du package de stratégie, ce qui vous permet d’identifier facilement les stratégies liées à un package de stratégie. Par exemple, lorsque vous attribuez le package de stratégie de travailleur clinique de santé aux médecins au sein de votre organisation, une stratégie nommée Healthcare_ClinicalWorker est créée pour chaque stratégie dans le package.

![Capture d’écran des politiques dans l’offre pour le travail clinique de santé](media/policy-packages-healthcare-clinical-worker.png)

## <a name="get-started-with-policy-packages"></a>Découvrir les packages de stratégie

Pour vous aider à prendre en main les packages de stratégie de santé, sur le concentrateur Microsoft Admin Center, sélectionnez **santé** , puis sélectionnez **affecter des paramètres de stratégie par rôle**. Lorsque vous êtes prêt à commencer, déterminez les packages de stratégie auxquels vous souhaitez affecter des personnes à votre organisation.

Pour en savoir plus sur les stratégies spécifiques d’un package et leurs paramètres respectifs, sélectionnez **afficher les détails** de la stratégie. Celles-ci [peuvent être personnalisées](manage-policy-packages.md#customize-policies-in-a-policy-package) après affectation dans le centre d’administration Teams.

Sélectionnez un ou plusieurs packages à attribuer, puis cliquez sur **suivant**. Vous pouvez rechercher et ajouter des personnes au package de stratégie qui conviennent le mieux à leur rôle. Un individu ne peut pas être attribué à plusieurs packages de stratégies en même temps.

Une fois que vous avez ajouté des personnes au package de stratégie approprié, **Terminer** finalise vos sélections. Vous pouvez continuer à personnaliser et gérer des packages de stratégie dans le centre d’administration Microsoft Teams.

## <a name="manage-policy-packages"></a>Gérer vos packages de stratégie

### <a name="view"></a>Afficher

Affichez les paramètres de chaque stratégie d’un package de stratégie avant d’assigner un package. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **packages de stratégie** , sélectionnez le nom du package, puis sélectionnez le nom de la stratégie.

Déterminez si les valeurs prédéfinies conviennent à votre organisation, ou si vous avez besoin de les personnaliser en fonction de vos besoins en matière de votre organisation.

### <a name="customize"></a>Personnaliser

Personnalisez les paramètres des stratégies dans le package de stratégie, si nécessaire, pour répondre aux besoins de votre organisation. Les modifications que vous apportez aux paramètres de stratégie s’appliquent automatiquement aux utilisateurs qui ont reçu le package. Pour modifier les paramètres d’une stratégie dans un package de stratégie, dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **packages de stratégie** , sélectionnez le package de stratégie, sélectionnez le nom de la stratégie que vous voulez modifier, puis sélectionnez **modifier**.

Gardez à l’esprit que vous pouvez également modifier les paramètres des stratégies d’un package après avoir affecté le package de stratégie. Pour en savoir plus, voir [personnaliser des stratégies dans un package de stratégie](manage-policy-packages.md#customize-policies-in-a-policy-package).

### <a name="assign"></a>Assignation

Attribuez le package de stratégie aux utilisateurs. Si une stratégie est affectée à un utilisateur et que vous affectez une autre stratégie, l’affectation la plus récente est prioritaire.

#### <a name="assign-a-policy-package-to-one-or-several-users"></a>Assigner un package de stratégie à un ou plusieurs utilisateurs

Pour attribuer un package de stratégie à un ou plusieurs utilisateurs, dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, sélectionnez **packages de stratégie** , puis **gérer les utilisateurs**.  

![Capture d’écran de l’affectation d’un package de stratégie dans le centre d’administration](media/policy-packages-healthcare-assign.png)

Pour en savoir plus, voir [attribuer un package de stratégie](manage-policy-packages.md#assign-a-policy-package).

Si une stratégie est affectée à un utilisateur et que vous affectez une autre stratégie, l’affectation la plus récente est prioritaire.

#### <a name="assign-a-policy-package-to-a-group"></a>Assigner un package de stratégie à un groupe

**Cette fonctionnalité est en version préliminaire privée**

Attribution de package de stratégie aux groupes vous permettent d’affecter plusieurs stratégies à un groupe d’utilisateurs, tel qu’un groupe de sécurité ou une liste de distribution. L’affectation de stratégie est propagée aux membres du groupe conformément aux règles de priorité. Les membres étant ajoutés ou supprimés d’un groupe, leurs affectations de stratégie héritées sont mises à jour en conséquence. Cette méthode est recommandée pour les groupes d’utilisateurs 50 000, mais fonctionne aussi avec des groupes de plus grande taille.

Pour en savoir plus, voir [attribuer un package de stratégie à un groupe](assign-policies.md#assign-a-policy-package-to-a-group).

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a>Assigner un package de stratégie à un grand jeu (lot) d’utilisateurs

Utilisez une affectation de package de stratégie de lot pour assigner un package de stratégie à un grand nombre d’utilisateurs à la fois. Vous utilisez l’applet de commande [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) pour transmettre un lot d’utilisateurs et le package de stratégie que vous voulez affecter. Les affectations sont traitées en tant qu’opérations en arrière-plan et chaque lot est généré.

Un lot peut contenir jusqu’à 5 000 utilisateurs. Vous pouvez spécifier des utilisateurs en fonction de leur ID d’objet, de leur nom d’utilisateur principal, de leur adresse SIP ou de leur adresse de messagerie. Pour en savoir plus, voir [affecter un package de stratégie à un lot d’utilisateurs](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).

## <a name="related-topics"></a>Sujets associés

[Gérer les packages de stratégie dans Teams](manage-policy-packages.md)

[Attribuer des stratégies à vos utilisateurs dans teams](assign-policies.md)
