---
title: Gérer les stratégies de voix et d’appel dans Teams
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Découvrez Teams stratégies de voix et d’appels.
audience: admin
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8a63aa772d94a4a385301315d1c1bd3b6488fa3b
ms.sourcegitcommit: 9532eb79310cd653010565607fa394f2b8dd182d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/23/2022
ms.locfileid: "65646463"
---
# <a name="manage-voice-and-calling-policies-in-microsoft-teams"></a>Gérer les stratégies de voix et d’appel dans Microsoft Teams

Les stratégies de voix et d’appel sont utilisées pour contrôler la voix et les appels dans Microsoft Teams.

## <a name="emergency-calling-policies"></a>Stratégies d’appel d’urgence

Vous utilisez des [stratégies d’appel d’urgence](manage-emergency-calling-policies.md) pour configurer ce qui se passe lorsqu’un utilisateur de votre organisation effectue un appel d’urgence. Ces stratégies sont gérées dans le centre d’administration Teams ou à l’aide de Windows PowerShell.

![Capture d’écran de la stratégie d’appel d’urgence.](media/emergency-calling-policy2.png)

## <a name="emergency-call-routing-policies"></a>Stratégies de routage des appels d’urgence

Si votre organisation a déployé **Système téléphonique routage direct**, vous pouvez utiliser des [stratégies de routage des appels d’urgence](manage-emergency-call-routing-policies.md) pour déterminer où les appels d’urgence sont acheminés, si les services d’urgence améliorés sont activés et quels numéros sont utilisés pour les services d’urgence. Ces stratégies sont gérées à l’aide de PowerShell ou dans le centre d’administration Microsoft Teams.

![Capture d’écran de la stratégie de routage des appels d’urgence.](media/emergency-call-routing-policy.png)

## <a name="caller-id-policies"></a>Stratégies d’ID d’appelant

[Les stratégies d’ID](caller-id-policies.md) d’appelant sont utilisées pour modifier ou bloquer l’ID de l’appelant.

![Capture d’écran de la stratégie d’ID de l’appelant.](media/caller-id-policy.png)

## <a name="voice-routing-policies"></a>Stratégies de routage vocal

Une [stratégie de routage vocal](manage-voice-routing-policies.md) est un conteneur pour les enregistrements d’utilisation du réseau téléphonique commuté (RTC). Vous pouvez utiliser ces stratégies si votre organisation a déployé **Système téléphonique routage direct**. Les stratégies de routage vocal peuvent être gérées avec PowerShell ou dans le centre d’administration Teams.

![Capture d’écran de la stratégie de routage vocal.](media/voice-routing-policy.png)

## <a name="calling-policies"></a>Stratégies d’appel

[Les stratégies d’appel](teams-calling-policy.md) contrôlent les fonctionnalités d’appel et de transfert d’appel disponibles pour les utilisateurs, notamment si un utilisateur peut passer des appels privés, envoyer des appels à des groupes d’appels et acheminer les appels vers la messagerie vocale.

![Capture d’écran de la stratégie d’appel.](media/calling-policy.png)

## <a name="call-park-and-retrieve-policies"></a>Appeler des stratégies de parc et récupérer

[L’appel par parcage et récupération](call-park-and-retrieve.md) permet aux utilisateurs de mettre d’autres utilisateurs en attente et permet au même utilisateur ou à quelqu’un d’autre de continuer l’appel.

![Capture d’écran du parc d’appels et de la stratégie de récupération.](media/call-park-policy.png)

## <a name="create-and-manage-dial-plans"></a>Créer et gérer les plans de numérotation

[Les plans de numérotation](create-and-manage-dial-plans.md) traduisent les numéros de téléphone composés pour l’autorisation et le routage des appels. Vous pouvez créer et gérer des plans de numérotation via PowerShell ou dans le centre d’administration Microsoft Teams.

![Capture d’écran du plan de numérotation.](media/dial-plans.png)

## <a name="related-topics"></a>Voir aussi

* [Gérer les stratégies d’appel d’urgence dans Microsoft Teams](manage-emergency-calling-policies.md)
* [Gérer les stratégies de routage d’appel d’urgence](manage-emergency-call-routing-policies.md)
* [Gérer les stratégies d’ID d’appelant dans Microsoft Teams](caller-id-policies.md)
* [Gérer les stratégies de routage vocal](manage-voice-routing-policies.md)
* [Stratégies de conservation dans Microsoft Teams](teams-calling-policy.md)
* [Parcage et récupération d’appel dans Microsoft Teams](call-park-and-retrieve.md)
* [Créer et gérer les plans de numérotation](create-and-manage-dial-plans.md)
* [Gérer Teams avec des stratégies](manage-teams-with-policies.md)
