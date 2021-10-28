---
title: Gérer les Teams des stratégies
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: En savoir plus sur Teams stratégies.
audience: admin
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a08e48a37b90a7d8a99053d01a844c3451314e00
ms.sourcegitcommit: 3a8bec0445cee5cd776fb1991f093a0ec4351852
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/28/2021
ms.locfileid: "60605590"
---
# <a name="manage-teams-with-policies"></a>Gérer les Teams des stratégies

Les stratégies sont un élément important de la gestion des Teams. Utilisez cet article pour naviguer dans l’utilisation des stratégies au profit de votre organisation.

## <a name="what-you-use-policies-for"></a>Utilisation des stratégies pour

Les stratégies sont utilisées pour effectuer de nombreuses tâches au sein de votre organisation dans différents domaines tels que la messagerie, les réunions et les applications. Vous pouvez notamment autoriser les utilisateurs à planifier des réunions dans un canal d’équipe, permettre aux utilisateurs de modifier les messages envoyés et contrôler si les utilisateurs peuvent épingler des applications à la barre d’application Teams.

## <a name="how-to-assign-policies"></a>Comment affecter des stratégies

Les stratégies peuvent être affectées de différentes manières en fonction de ce que votre organisation tente d’accomplir. Vous pouvez rendre et afficher les devoirs dans le Teams d’administration.

![Capture d’écran de l’affectation d’une stratégie de groupe.](media/group-policy-assignment.png)

En savoir plus sur l’attribution des [stratégies ici.](policy-assignment-overview.md)

## <a name="how-to-manage-policies"></a>Comment gérer les stratégies

Les stratégies sont gérées avec le centre Microsoft Teams’administration de l’entreprise [ou à l’aide de PowerShell.](./teams-powershell-managing-teams.md#manage-policies-via-powershell)

Par exemple, une stratégie de configuration d’application peut vous permettre de permettre aux utilisateurs de télécharger des applications personnalisées, d’installer des applications pour le compte de vos utilisateurs et d’épingler des applications à la barre d’application Teams. Ces stratégies sont configurées dans le Teams d’administration.

![Capture d’écran de la stratégie de configuration de l’application.](media/app-setup-policy.png)

En outre, une stratégie de réunion peut être utilisée pour contrôler les paramètres audio et vidéo dans les réunions Teams telles que les transcriptions, les enregistrements cloud et les enregistrements IP audio/vidéo.

![Capture d’écran de la stratégie de réunion.](media/engineering-meeting-policy.png)

### <a name="teams-for-education"></a>Teams pour l’éducation

Vous pouvez également utiliser [l’Assistant Stratégie Teams pour l'éducation](easy-policy-setup-edu.md) pour configurer et gérer facilement des stratégies pour votre environnement d’apprentissage.

![Capture d’écran Teams pour l'éducation’Assistant Stratégie.](media/easy-policy-setup-quick-setup.png)

## <a name="types-of-policies"></a>Types de stratégies

Les stratégies suivantes peuvent être gérées avec Microsoft Teams.

Type de stratégie | Description
------------|------------
[Packages de stratégie](manage-policy-packages.md) | Un package de stratégie dans Microsoft Teams est un ensemble de stratégies et de paramètres prédéfinés que vous pouvez affecter aux utilisateurs ayant des rôles similaires dans votre organisation.
[Stratégies de réunion](meeting-policies-overview.md) | Une stratégie de réunion permet de contrôler les fonctionnalités disponibles pour les participants à la réunion prévues par les utilisateurs de votre organisation. Les stratégies de réunion incluent les rubriques suivantes.<br> - Stratégies audio et vidéo<br> - Stratégies de partage de contenu et d’écran<br> - Stratégies d’accès, invités et participants<br> - Politiques générales
[Stratégies de voix et d’appel](voice-and-calling-policies.md)| Les stratégies de voix et d’appel gèrent ces paramètres via les équipes, telles que les appels d’urgence, le routage des appels et l’ID d’appelant.
[Stratégies d’application](app-policies.md)| Les stratégies d’application sont utilisées pour contrôler les applications dans Microsoft Teams. Les administrateurs peuvent autoriser ou bloquer les applications que les utilisateurs peuvent installer, épingler des applications à la barre d’application Teams d’un utilisateur et installer une application pour le compte de vos utilisateurs.
[Stratégies de messagerie](messaging-policies-in-teams.md)| Les stratégies de messagerie contrôlent la disponibilité des fonctionnalités de conversation et de canal.

## <a name="related-topics"></a>Sujets associés

* [Attribuer des stratégies dans Teams - mise en place](policy-assignment-overview.md)
* [Gérer les stratégies de commentaires dans Microsoft Teams](manage-feedback-policies-in-teams.md)
* [Gérer les stratégies d’équipes dans Microsoft Teams](teams-policies.md)
* [Configurer des événements en direct dans Microsoft Teams](teams-live-events/set-up-for-teams-live-events.md)
* [Teams pour l'éducation stratégies et packages de stratégies](policy-packages-edu.md)