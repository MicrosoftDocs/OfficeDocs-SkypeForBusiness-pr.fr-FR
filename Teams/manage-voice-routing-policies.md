---
title: Gérer les stratégies de routage vocal pour le routage direct
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Découvrez comment créer et gérer des stratégies de routage voix dans Microsoft Teams.
ms.openlocfilehash: 1717f1b0400f67346034bd9e92bd698305fdd324
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58727093"
---
# <a name="manage-voice-routing-policies-for-direct-routing"></a>Gérer les stratégies de routage vocal pour le routage direct

Si vous avez déployé [Système téléphonique Direct Routing](direct-routing-landing-page.md) dans votre organisation, vous utilisez les stratégies de routage vocal pour autoriser les utilisateurs de Teams et Skype Entreprise Online à recevoir et à passer des appels téléphoniques vers le réseau téléphonique commuté (PSTN) à l’aide de votre infrastructure téléphonique locale.

Une stratégie de routage vocal est un conteneur pour les enregistrements d’utilisation PSTN. Pour créer et gérer des stratégies de routage voix, vous devez vous rendre sur les stratégies de routage de **Voice** Voice dans le Centre d’administration Microsoft Teams’administration ou à l’aide  >   de Windows PowerShell.

Vous pouvez utiliser la stratégie globale (par défaut à l’échelle de l’organisation) ou créer et attribuer des stratégies personnalisées. Les utilisateurs obtiennent automatiquement la stratégie globale, sauf si vous créez et attribuez une stratégie personnalisée. N’oubliez pas que vous pouvez modifier les paramètres de la stratégie globale, mais que vous ne pouvez pas le renommer ou le supprimer.

Il est important de savoir que l’affectation d’une stratégie de routage vocal à un utilisateur ne l’autorise pas à effectuer des appels PSTN dans Teams. Vous devrez également activer l’utilisateur pour effectuer Système téléphonique routage direct et effectuer d’autres étapes de configuration. Pour plus d’informations, [voir Configurer le routage direct.](direct-routing-configure.md)

## <a name="create-a-custom-voice-routing-policy"></a>Créer une stratégie de routage vocal personnalisée

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

1. Dans le panneau de navigation de gauche du Microsoft Teams d’administration, allez dans les stratégies de routage de **Voice**  >  **Voice,** puis cliquez sur **Ajouter.**<br>
    ![Capture d’écran de la page Ajouter une stratégie de routage vocal dans Microsoft Teams d’administration.](media/manage-voice-routing-policies.png) 
2. Entrez un nom pour votre stratégie, ainsi qu’une description.
3. Sous **Enregistrements d’utilisation PSTN,** cliquez sur Ajouter une utilisation **PSTN,** puis sélectionnez les enregistrements à ajouter. Si vous avez besoin de créer un enregistrement d’utilisation PSTN, cliquez sur **Ajouter.**
4. Si vous avez ajouté plusieurs enregistrements d’utilisation PSTN, organisez-les dans l’ordre de votre choix.
5. Lorsque vous avez terminé, cliquez sur **Appliquer.**
6. Cliquez sur **Enregistrer**.

### <a name="using-powershell"></a>Utiliser PowerShell

Voir [New-CsOnlineVoiceRoutingPolicy.](/powershell/module/skype/new-csonlinevoiceroutingpolicy)

## <a name="edit-a-voice-routing-policy"></a>Modifier une stratégie de routage vocal

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

Vous pouvez modifier la stratégie globale ou toutes les stratégies personnalisées que vous créez.

1. Dans le panneau de navigation de gauche du Microsoft Teams d’administration, allez **dans** les stratégies  >  **de routage de Voice Voice.**
2. Sélectionnez la stratégie en cliquant à gauche du nom de celle-ci, puis cliquez sur **Modifier**.
3. Cliquez **sur Ajouter/supprimer des enregistrements d’utilisation PSTN,** a apporter les modifications de votre souhaitez, puis cliquez sur **Enregistrer.**

### <a name="using-powershell"></a>Utiliser PowerShell

Voir [Set-CsOnlineVoiceRoutingPolicy.](/powershell/module/skype/set-csonlinevoiceroutingpolicy)

## <a name="assign-a-custom-voice-routing-policy-to-users"></a>Affecter une stratégie de routage vocal personnalisée aux utilisateurs

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Voir également [Grant-CsOnlineVoiceRoutingPolicy.](/powershell/module/skype/grant-csonlinevoiceroutingpolicy)

## <a name="related-topics"></a>Sujets associés

[Présentation de Teams PowerShell](teams-powershell-overview.md)

[Configurer le routage vocal pour le routage direct](direct-routing-voice-routing.md)

[Activer le routage géodépendant pour le routage direct](location-based-routing-enable.md)

[Attribuer des stratégies à vos utilisateurs](assign-policies.md)