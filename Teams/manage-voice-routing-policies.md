---
title: Gérer les stratégies de routage vocal dans Microsoft Teams
author: cichur
ms.author: v-cichur
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
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment créer et gérer des stratégies de routage vocal dans Microsoft Teams.
ms.openlocfilehash: 00b70363f0034ebc8d99aa59e037658e406af2a5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802554"
---
# <a name="manage-voice-routing-policies-in-microsoft-teams"></a>Gérer les stratégies de routage vocal dans Microsoft Teams

Si vous avez [](direct-routing-landing-page.md) déployé le routage direct du système téléphonique dans votre organisation, vous utilisez les stratégies de routage vocal pour permettre aux utilisateurs de Teams et de Skype Entreprise Online de recevoir et de passer des appels téléphoniques vers le réseau téléphonique commuté (PSTN) à l’aide de votre infrastructure téléphonique locale.

Une stratégie de routage vocal est un conteneur pour les enregistrements d’utilisation PSTN. Pour créer et gérer des stratégies de routage voix, vous devez vous rendre sur les stratégies de routage de voix dans le Centre d’administration de Microsoft Teams ou à l’aide  >   de Windows PowerShell.

Vous pouvez utiliser la stratégie globale (par défaut à l’échelle de l’organisation) ou créer et attribuer des stratégies personnalisées. Les utilisateurs obtiennent automatiquement la stratégie globale, sauf si vous créez et attribuez une stratégie personnalisée. N’oubliez pas que vous pouvez modifier les paramètres de la stratégie globale, mais que vous ne pouvez pas le renommer ou le supprimer.

Il est important de savoir que l’affectation d’une stratégie de routage vocal à un utilisateur ne l’autorise pas à effectuer des appels PSTN dans Teams. Vous devrez également activer le routage direct de l’utilisateur pour Phone System et effectuer d’autres étapes de configuration. Pour plus d’informations, [voir Configurer le routage direct.](direct-routing-configure.md)

## <a name="create-a-custom-voice-routing-policy"></a>Créer une stratégie de routage vocal personnalisée

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

1. Dans le panneau de navigation gauche du Centre d’administration Microsoft Teams, allez sur Stratégies de routage de **Voice**  >  **Voice,** puis cliquez sur **Ajouter.**<br>
    ![Capture d’écran de la page Ajouter une stratégie de routage vocal dans le Centre d’administration Microsoft Teams ](media/manage-voice-routing-policies.png) 
2. Entrez un nom pour votre stratégie, ainsi qu’une description.
3. Sous **Enregistrements d’utilisation PSTN,** cliquez sur Ajouter une utilisation **PSTN,** puis sélectionnez les enregistrements à ajouter. Si vous avez besoin de créer un enregistrement d’utilisation PSTN, cliquez sur **Ajouter.**
4. Si vous avez ajouté plusieurs enregistrements d’utilisation PSTN, organisez-les dans l’ordre de votre choix.
5. Lorsque vous avez terminé, cliquez sur **Appliquer.**
6. Cliquez sur **Enregistrer**.

### <a name="using-powershell"></a>Utiliser PowerShell

Voir [New-CsOnlineVoiceRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy)

## <a name="edit-a-voice-routing-policy"></a>Modifier une stratégie de routage vocal

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

Vous pouvez modifier la stratégie globale ou toutes les stratégies personnalisées que vous créez.

1. Dans le panneau de navigation gauche du Centre d’administration Microsoft Teams, allez aux stratégies de routage de **Voice**  >  **Voice.**
2. Sélectionnez la stratégie en cliquant à gauche du nom de celle-ci, puis cliquez sur **Modifier**.
3. Cliquez **sur Ajouter/supprimer des enregistrements d’utilisation PSTN,** a apporter les modifications de votre souhaitez, puis cliquez sur **Enregistrer.**

### <a name="using-powershell"></a>Utiliser PowerShell

Voir [Set-CsOnlineVoiceRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy)

## <a name="assign-a-custom-voice-routing-policy-to-users"></a>Affecter une stratégie de routage vocal personnalisée aux utilisateurs

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Voir également [Grant-CsOnlineVoiceRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy)

## <a name="related-topics"></a>Sujets associés

[Présentation de Teams PowerShell](teams-powershell-overview.md)

[Configurer le routage vocal pour le routage direct](direct-routing-voice-routing.md)

[Activer le routage géodépendant pour le routage direct](location-based-routing-enable.md)

[Attribuer des stratégies à vos utilisateurs](assign-policies.md)
