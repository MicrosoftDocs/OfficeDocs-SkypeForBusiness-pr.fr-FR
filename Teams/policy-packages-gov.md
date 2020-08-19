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
ms.openlocfilehash: 738197a82303c1149ebc89a8e3ad7c6b37df90eb
ms.sourcegitcommit: bd13aecbb25c14e17d1b64343df6d80c90b2aa45
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/19/2020
ms.locfileid: "46804018"
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

Affichez les paramètres de chaque stratégie d’un package de stratégie avant d’assigner un package. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, sélectionnez **packages de stratégie**, sélectionnez le nom du package, puis sélectionnez le nom de la stratégie.

Déterminez si les valeurs prédéfinies conviennent à votre organisation, ou si vous avez besoin de les personnaliser en fonction de vos besoins en matière de votre organisation.

### <a name="customize"></a>Personnaliser

Personnalisez les paramètres des stratégies dans le package de stratégie, si nécessaire, pour répondre aux besoins de votre organisation. Les modifications que vous apportez aux paramètres de stratégie s’appliquent automatiquement aux utilisateurs qui ont reçu le package. Pour modifier les paramètres d’une stratégie dans un package de stratégie, dans le centre d’administration de Microsoft Teams, sélectionnez le package de stratégie, sélectionnez le nom de la stratégie que vous voulez modifier, puis sélectionnez **modifier**.

Gardez à l’esprit que vous pouvez également modifier les paramètres des stratégies d’un package après avoir affecté le package de stratégie. Pour en savoir plus, voir [personnaliser des stratégies dans un package de stratégie](manage-policy-packages.md#customize-policies-in-a-policy-package). 

### <a name="assign"></a>Assignation

Attribuez le package de stratégie aux utilisateurs. Pour attribuer un package de stratégie à un ou plusieurs utilisateurs, cliquez sur **gérer les utilisateurs**. Vous pouvez également [Utiliser PowerShell](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) pour assigner un package de stratégie aux grands groupes d’utilisateurs. 

Pour plus d’informations sur l’affectation d’un package de stratégie à l’aide du centre d’administration Microsoft teams ou de PowerShell, voir [affecter un package de stratégie](manage-policy-packages.md#assign-a-policy-package).

![Capture d’écran de l’affectation d’un package de stratégie dans le centre d’administration](media/policy-packages-gov-assign.png)

Si une stratégie est affectée à un utilisateur et que vous affectez une autre stratégie, l’affectation la plus récente est prioritaire.

## <a name="related-topics"></a>Sujets associés

[Gérer les packages de stratégie dans Teams](manage-policy-packages.md)

[Attribuer des stratégies à vos utilisateurs dans teams](assign-policies.md) 
