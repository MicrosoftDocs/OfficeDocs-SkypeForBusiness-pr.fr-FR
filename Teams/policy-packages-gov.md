---
title: Packages de stratégie d’équipes pour le secteur public
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
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser et gérer des packages de stratégie d’équipe pour votre organisation gouvernementale.
ms.openlocfilehash: 8ef632689cb52180e8fd18cf4047fb9a25150885
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908593"
---
# <a name="teams-policy-packages-for-government"></a>Packages de stratégie d’équipes pour le secteur public

> [!NOTE]
> Pour le moment, les packages de stratégie ne sont pas disponibles dans les déploiements Microsoft 365 Government High ou DoD.

## <a name="overview"></a>Vue d’ensemble

Un [package de stratégie](manage-policy-packages.md) dans Microsoft teams est un ensemble de stratégies et de paramètres de stratégie prédéfinis que vous pouvez affecter aux utilisateurs ayant des rôles similaires au sein de votre organisation. Les packages de stratégie simplifient, rationalisent et garantissent la cohérence lors de la gestion des stratégies. Vous pouvez personnaliser les paramètres des stratégies du package selon les besoins de vos utilisateurs. Lorsque vous modifiez les paramètres des stratégies dans un package de stratégie, tous les utilisateurs assignés à ce package obtiennent les paramètres mis à jour. Vous pouvez gérer des packages de stratégie à l’aide du centre d’administration Microsoft teams ou de PowerShell.

Les packages de stratégie prédéfinis pour les éléments suivants, en fonction du package :

- Messagerie
- Réunions
- Appel
- Configuration de l’application
- Événements en direct

Teams inclut actuellement les packages de stratégie suivants pour le gouvernement.

|Nom du package dans le centre d’administration Microsoft teams|Idéal pour|Description |
|---------|---------|---------|
|Officier de sûreté public  |Fonctionnaires de la sécurité publique au sein de votre organisation gouvernementale  |Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux responsables de la sécurité publique au sein de votre organisation. |
|Gestionnaire de terrain  |Responsables terrain au sein de votre organisation gouvernementale |Crée un ensemble de stratégies et applique ces paramètres aux responsables terrain de votre organisation.|
|Collaborateur terrain  |Terrain travailleurs de votre organisation gouvernementale |Crée un ensemble de stratégies et applique ces paramètres aux travailleurs terrain au sein de votre organisation.|

![Capture d’écran des packages de politique de santé](media/policy-packages-gov.png)

Chaque stratégie individuelle dispose du nom du package de stratégie, ce qui vous permet d’identifier facilement les stratégies liées à un package de stratégie. Par exemple, lorsque vous attribuez le package de stratégie de l’officier de sécurité public aux utilisateurs de votre organisation, une stratégie nommée PublicSafety_Officer est créée pour chaque stratégie dans le package.

![Capture d’écran des politiques dans l’offre pour le travail clinique de santé](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a>Gérer vos packages de stratégie

### <a name="view"></a>Afficher

Affichez les paramètres de chaque stratégie d’un package de stratégie avant d’assigner un package. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, sélectionnez **packages de stratégie** , sélectionnez le nom du package, puis sélectionnez le nom de la stratégie.

Déterminez si les valeurs prédéfinies conviennent à votre organisation, ou si vous avez besoin de les personnaliser en fonction de vos besoins en matière de votre organisation.

### <a name="customize"></a>Personnaliser

Personnalisez les paramètres des stratégies dans le package de stratégie, si nécessaire, pour répondre aux besoins de votre organisation. Les modifications que vous apportez aux paramètres de stratégie s’appliquent automatiquement aux utilisateurs qui ont reçu le package. Pour modifier les paramètres d’une stratégie dans un package de stratégie, dans le centre d’administration de Microsoft Teams, sélectionnez le package de stratégie, sélectionnez le nom de la stratégie que vous voulez modifier, puis sélectionnez **modifier**.

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
