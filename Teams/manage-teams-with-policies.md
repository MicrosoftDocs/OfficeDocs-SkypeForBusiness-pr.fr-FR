---
title: Gérer Teams avec des stratégies
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Penchez-vous sur Teams stratégies.
audience: admin
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 932fed6b2a735aabee0511b6f1c6b863e01e403c
ms.sourcegitcommit: 9532eb79310cd653010565607fa394f2b8dd182d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/23/2022
ms.locfileid: "65646483"
---
# <a name="manage-teams-with-policies"></a>Gérer Teams avec des stratégies

Les stratégies sont un élément important de la gestion des Teams. Cet article explique comment utiliser des stratégies pour bénéficier à votre organisation.

## <a name="what-you-use-policies-for"></a>À quoi servent les stratégies

Les stratégies sont utilisées pour accomplir de nombreuses tâches au sein de votre organisation dans différents domaines, tels que la messagerie, les réunions et les applications. Vous pouvez notamment autoriser les utilisateurs à planifier des réunions dans un canal Teams, permettre aux utilisateurs de modifier les messages envoyés et contrôler si les utilisateurs peuvent épingler des applications à la barre d’applications Teams.

## <a name="how-to-assign-policies"></a>Comment attribuer des stratégies

Les stratégies peuvent être affectées de plusieurs manières différentes en fonction de ce que votre organisation tente d’accomplir. Vous pouvez effectuer et afficher les affectations dans le centre d’administration Teams.

![Capture d’écran de l’attribution de stratégie de groupe.](media/group-policy-assignment.png)

En savoir plus sur l’attribution de stratégies [ici](policy-assignment-overview.md).

## <a name="how-to-manage-policies"></a>Guide pratique pour gérer les stratégies

Les stratégies sont gérées avec le centre d’administration Microsoft Teams ou [à l’aide de PowerShell](./teams-powershell-managing-teams.md#manage-policies-via-powershell).

Par exemple, une stratégie d’installation d’application peut vous permettre de permettre aux utilisateurs de charger des applications personnalisées, d’installer des applications pour le compte de vos utilisateurs et d’épingler des applications à la barre d’applications Teams. Ces stratégies sont configurées dans le centre d’administration Teams.

![Capture d’écran de la stratégie d’installation de l’application.](media/app-setup-policy.png)

En outre, une stratégie de réunion peut être utilisée pour contrôler les paramètres audio et vidéo dans Teams réunions telles que les transcriptions, les enregistrements cloud et l’audio/vidéo IP.

![Capture d’écran de la stratégie de réunion.](media/engineering-meeting-policy.png)

### <a name="teams-for-education"></a>Teams pour l’éducation

Vous pouvez également utiliser [l’Assistant stratégie Teams pour l'éducation](easy-policy-setup-edu.md) pour configurer et gérer facilement des stratégies pour votre environnement d’apprentissage.

![Capture d’écran de Teams pour l'éducation Assistant Stratégie.](media/easy-policy-setup-quick-setup.png)

## <a name="types-of-policies"></a>Types de stratégies

Les stratégies suivantes peuvent être gérées avec Microsoft Teams.

Type de stratégie | Description
------------|------------
[Packages de stratégie](manage-policy-packages.md) | Un package de stratégie dans Microsoft Teams est une collection de stratégies et de paramètres prédéfinis que vous pouvez attribuer aux utilisateurs qui ont des rôles similaires dans votre organisation.
[Stratégies de réunion](meeting-policies-overview.md) | Une stratégie de réunion est utilisée pour contrôler les fonctionnalités disponibles pour les participants aux réunions planifiées par les utilisateurs de votre organisation. Les stratégies de réunion incluent les rubriques suivantes.<br> - Stratégies audio et vidéo<br> - Stratégies de partage de contenu et d’écran<br> - Participants, invités et stratégies d’accès<br> - Stratégies générales
[Stratégies de voix et d’appel](voice-and-calling-policies.md)| Les stratégies de voix et d’appel gèrent ces paramètres par le biais d’équipes telles que les appels d’urgence, le routage des appels et l’ID d’appelant.
[Stratégies d’application](app-policies.md)| Les stratégies d’application sont utilisées pour contrôler les applications dans Microsoft Teams. Les administrateurs peuvent autoriser ou bloquer les applications que les utilisateurs peuvent installer, épingler des applications à la barre d’applications Teams d’un utilisateur et installer l’application pour le compte de vos utilisateurs.
[Stratégies de messagerie](messaging-policies-in-teams.md)| Les stratégies de messagerie contrôlent la disponibilité des fonctionnalités de conversation et de canal.

## <a name="related-topics"></a>Voir aussi

* [Affecter des stratégies dans Teams - Prise en main](policy-assignment-overview.md)
* [Gérer les stratégies de commentaires dans Microsoft Teams](manage-feedback-policies-in-teams.md)
* [Gérer les stratégies d’équipe dans Microsoft Teams](teams-policies.md)
* [Configurer des événements en direct dans Microsoft Teams](teams-live-events/set-up-for-teams-live-events.md)
* [Teams pour l'éducation les stratégies et les packages de stratégie](policy-packages-edu.md)