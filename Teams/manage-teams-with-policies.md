---
title: Gérer Teams avec des stratégies
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Penchez-vous sur les stratégies Teams.
audience: admin
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.collection:
- M365-collaboration
ms.openlocfilehash: acaa1280e00ad2e86a49c2bbd8e7f4464bd0c0e7
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268759"
---
# <a name="manage-teams-with-policies"></a>Gérer Teams avec des stratégies

Les stratégies sont un élément important de la gestion de Teams. Cet article explique comment utiliser des stratégies pour bénéficier à votre organisation.

## <a name="what-you-use-policies-for"></a>À quoi servent les stratégies

Les stratégies sont utilisées pour accomplir de nombreuses tâches au sein de votre organisation dans différents domaines, tels que la messagerie, les réunions et les applications. Vous pouvez notamment autoriser les utilisateurs à planifier des réunions dans un canal Teams, permettre aux utilisateurs de modifier les messages envoyés et contrôler si les utilisateurs peuvent épingler des applications à la barre des applications Teams.

## <a name="how-to-assign-policies"></a>Comment attribuer des stratégies

Les stratégies peuvent être affectées de plusieurs manières différentes en fonction de ce que votre organisation tente d’accomplir. Vous pouvez effectuer et afficher les affectations dans le Centre d’administration Teams.

:::image type="content" source="media/group-policy-assignment.png" alt-text="Capture d’écran de l’attribution de stratégie de groupe Teams." lightbox="media/group-policy-assignment.png":::

En savoir plus sur l’attribution de stratégies [ici](policy-assignment-overview.md).

> [!NOTE]
> Pour annuler l’affectation de stratégies, vous pouvez supprimer des affectations en bloc pour tous les utilisateurs directement affectés à une stratégie. Pour plus d’informations, lisez [les stratégies de désaffectation en bloc](assign-policies-users-and-groups.md#unassign-policies-in-bulk).

## <a name="how-to-manage-policies"></a>Guide pratique pour gérer les stratégies

Les stratégies sont gérées avec le Centre d’administration Microsoft Teams ou [à l’aide de PowerShell](./teams-powershell-managing-teams.md#manage-policies-via-powershell).

Par exemple, une stratégie d’installation d’application peut vous permettre de permettre aux utilisateurs de charger des applications personnalisées, d’installer des applications pour le compte de vos utilisateurs et d’épingler des applications à la barre des applications Teams. Ces stratégies sont configurées dans le Centre d’administration Teams.

:::image type="content" source="media/app-setup-policy.png" alt-text="Capture d’écran de la stratégie d’installation de l’application." lightbox="media/app-setup-policy.png":::

En outre, une stratégie de réunion peut être utilisée pour contrôler les paramètres audio et vidéo dans les réunions Teams, telles que les transcriptions, les enregistrements cloud et l’audio/vidéo IP.

:::image type="content" source="media/engineering-meeting-policy.png" alt-text="Capture d’écran de la stratégie de réunion." lightbox="media/engineering-meeting-policy.png":::

### <a name="teams-for-education"></a>Teams pour l’éducation

Vous pouvez également utiliser [l’Assistant stratégie Teams pour l'éducation](easy-policy-setup-edu.md) pour configurer et gérer facilement des stratégies pour votre environnement d’apprentissage.

:::image type="content" source="media/easy-policy-setup-quick-setup.png" alt-text="Capture d’écran de Teams pour l'éducation Assistant Stratégie." lightbox="media/easy-policy-setup-quick-setup.png":::

## <a name="types-of-policies"></a>Types de stratégies

Les stratégies suivantes peuvent être gérées avec Microsoft Teams.

Type de stratégie | Description
------------|------------
[Packages de stratégie](manage-policy-packages.md) | Un package de stratégie dans Microsoft Teams est un ensemble de stratégies et de paramètres prédéfinis que vous pouvez attribuer aux utilisateurs qui ont des rôles similaires dans votre organisation.
[Stratégies de réunion](meeting-policies-overview.md) | Une stratégie de réunion est utilisée pour contrôler les fonctionnalités disponibles pour les participants aux réunions planifiées par les utilisateurs de votre organisation. Les stratégies de réunion incluent les rubriques suivantes.<br> - Stratégies audio et vidéo<br> - Stratégies de partage de contenu et d’écran<br> - Participants, invités et stratégies d’accès<br> - Stratégies générales
[Stratégies de voix et d’appel](voice-and-calling-policies.md)| Les stratégies de voix et d’appel gèrent ces paramètres par le biais d’équipes telles que les appels d’urgence, le routage des appels et l’ID d’appelant.
[Stratégies d’application](app-policies.md)| Les stratégies d’application sont utilisées pour contrôler les applications dans Microsoft Teams. Les administrateurs peuvent autoriser ou bloquer les applications que les utilisateurs peuvent installer, épingler des applications à la barre d’applications Teams d’un utilisateur et installer l’application pour le compte de vos utilisateurs.
[Stratégies de messagerie](messaging-policies-in-teams.md)| Les stratégies de messagerie contrôlent la disponibilité des fonctionnalités de conversation et de canal.

## <a name="related-topics"></a>Voir aussi

* [Affecter des stratégies dans Teams - Prise en main](policy-assignment-overview.md)
* [Gérer les stratégies de commentaires dans Microsoft Teams](manage-feedback-policies-in-teams.md)
* [Gérer les stratégies teams dans Microsoft Teams](teams-policies.md)
* [Configurer des événements en direct dans Microsoft Teams](teams-live-events/set-up-for-teams-live-events.md)
* [Teams pour l'éducation les stratégies et les packages de stratégie](policy-packages-edu.md)