---
title: Gérer les stratégies d’équipes dans Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
description: Découvrez comment utiliser et gérer les stratégies d’équipes dans votre organisation pour contrôler ce que les utilisateurs peuvent faire dans les équipes et les canaux.
ms.openlocfilehash: 4c980f6881a1ec73131e35cae1f04bf33f844026dccb1c14045d8310e2c755a5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54321106"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a>Gérer les stratégies d’équipes dans Microsoft Teams

En tant qu’administrateur, vous pouvez utiliser les stratégies Teams dans Microsoft Teams pour contrôler ce que les utilisateurs de votre organisation peuvent faire dans les équipes et les canaux. Par exemple, vous pouvez définir si les utilisateurs sont autorisés à créer des canaux privés.

Vous gérez les stratégies Teams en Teams  >  **Teams stratégies** dans le Microsoft Teams d’administration Teams. Vous pouvez utiliser la stratégie globale (par défaut à l’échelle de l’organisation) ou créer et attribuer des stratégies personnalisées. Les utilisateurs de votre organisation recevront automatiquement la stratégie globale, sauf si vous créez et leur attribuez une stratégie personnalisée.

Vous pouvez modifier la stratégie globale ou créer et affecter une stratégie personnalisée. Une fois que vous avez modifié la stratégie globale ou attribué une stratégie, l’application des modifications peut prendre quelques heures.

## <a name="create-a-custom-teams-policy"></a>Créer une stratégie d’équipe personnalisée

1. Dans le panneau de navigation gauche du Microsoft Teams d’administration, voir Teams  >  **Teams stratégies.**
2. Cliquez sur **Ajouter**.
3. Entrez un nom pour votre stratégie, ainsi qu’une description.

    ![Capture d’écran des paramètres de stratégie Teams](media/teams-policies.png)
4. Activer ou désactiver la création <a name="createchannels"></a> de canaux **privés,** selon que vous voulez autoriser ou non les utilisateurs à créer des canaux privés.

5. Cliquez sur **Enregistrer**.

## <a name="edit-a-teams-policy"></a>Modifier une stratégie Teams

Vous pouvez modifier la stratégie globale ou toutes les stratégies personnalisées que vous créez.

1. Dans le panneau de navigation gauche du Microsoft Teams d’administration, voir Teams  >  **Teams stratégies.**
2. Sélectionnez la stratégie en cliquant à gauche du nom de celle-ci, puis cliquez sur **Modifier**.
3. Activer ou désactiver les paramètres de votre souhaitez, puis cliquez sur **Enregistrer.**

## <a name="assign-a-custom-teams-policy-to-users"></a>Affecter une stratégie d’équipe personnalisée aux utilisateurs

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>Voir aussi

[Canaux privés dans Teams](private-channels.md)

[Attribuer des stratégies à vos utilisateurs](assign-policies.md)

[New-CsTeamsChannelsPolicy](/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)