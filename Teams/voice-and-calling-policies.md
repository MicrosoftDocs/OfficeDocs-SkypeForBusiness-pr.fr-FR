---
title: Gérer les stratégies de voix et d’appel Teams
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Découvrez les stratégies Teams voix et d’appel.
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9056c9b81fcda9c0e7408c63b4af00c1aabbffd0
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460584"
---
# <a name="manage-voice-and-calling-policies-in-microsoft-teams"></a>Gérer les stratégies de voix et d’appel Microsoft Teams

Les stratégies de voix et d’appel sont utilisées pour contrôler la voix et les appels Microsoft Teams.

## <a name="emergency-calling-policies"></a>Stratégies d’appel d’urgence

Les stratégies [d’appel d’urgence](manage-emergency-calling-policies.md) vous permet de configurer ce qui se passe lorsqu’un utilisateur de votre organisation effectue un appel d’urgence. Ces stratégies sont gérées dans le Centre Teams’administration ou à l’aide Windows PowerShell.

![Capture d’écran de la stratégie d’appel d’urgence.](media/emergency-calling-policy2.png)

## <a name="emergency-call-routing-policies"></a>Stratégies de routage d’appel d’urgence

Si votre organisation **Système téléphonique** déployé un routage direct, vous pouvez utiliser des stratégies de [routage](manage-emergency-call-routing-policies.md) des appels d’urgence pour déterminer où les appels d’urgence sont acheminés, si les services d’urgence améliorés sont activés et les numéros utilisés pour les services d’urgence. Ces stratégies sont gérées à l’aide de PowerShell ou dans le Microsoft Teams d’administration.

![Capture d’écran de la stratégie de routage des appels d’urgence.](media/emergency-call-routing-policy.png)

## <a name="caller-id-policies"></a>Stratégies d’ID d’appelant

[Les stratégies d’ID d’appelant](caller-id-policies.md) sont utilisées pour modifier ou bloquer l’ID d’appelant.

![Capture d’écran de la stratégie d’ID d’appelant.](media/caller-id-policy.png)

## <a name="voice-routing-policies"></a>Stratégies de routage voix

Une [stratégie de routage vocal](manage-voice-routing-policies.md) est un conteneur pour les enregistrements d’utilisation de réseau téléphonique commuté (PSTN). Vous pouvez utiliser ces stratégies si votre organisation a déployé Système téléphonique **routage direct.** Les stratégies de routage voix peuvent être gérées avec PowerShell ou dans le Teams d’administration.

![Capture d’écran de la stratégie de routage vocal.](media/voice-routing-policy.png)

## <a name="calling-policies"></a>Stratégies d’appel

[](teams-calling-policy.md) Les stratégies d’appel contrôlent les fonctionnalités d’appel et de forwardage disponibles pour les utilisateurs, notamment la décision d’un utilisateur de passer des appels privés, d’envoyer des appels à des groupes d’appels et de router les appels vers la messagerie vocale.

![Capture d’écran de la stratégie d’appel.](media/calling-policy.png)

## <a name="call-park-and-retrieve-policies"></a>Stratégies de parc et de récupération des appels

[Le parc d’appel et la récupération](call-park-and-retrieve.md) permettent aux utilisateurs de mettre d’autres utilisateurs en attente et de permettre à ce même utilisateur ou à quelqu’un d’autre de continuer l’appel.

![Capture d’écran de la stratégie de récupération et de parc d’appel.](media/call-park-policy.png)

## <a name="create-and-manage-dial-plans"></a>Créer et gérer les plans de numérotation

[Les plans de numérotation](create-and-manage-dial-plans.md) traduisent les numéros de téléphone à composer pour l’autorisation d’appel et le routage. Vous pouvez créer et gérer des plans de numérotation via PowerShell ou dans le Microsoft Teams d’administration.

![Capture d’écran du plan de numérotation.](media/dial-plans.png)

## <a name="related-topics"></a>Sujets associés

* [Gérer les stratégies d’appels d’urgence Microsoft Teams](manage-emergency-calling-policies.md)
* [Gérer les stratégies de routage d’appel d’urgence](manage-emergency-call-routing-policies.md)
* [Gérer les stratégies d’ID d’appelant dans Microsoft Teams](caller-id-policies.md)
* [Gérer les stratégies de routage vocal](manage-voice-routing-policies.md)
* [Stratégies de conservation dans Microsoft Teams](teams-calling-policy.md)
* [Parcage et récupération d’appel dans Microsoft Teams](call-park-and-retrieve.md)
* [Créer et gérer les plans de numérotation](create-and-manage-dial-plans.md)
* [Gérer les Teams des stratégies](manage-teams-with-policies.md)
