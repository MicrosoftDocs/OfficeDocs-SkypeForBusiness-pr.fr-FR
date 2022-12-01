---
title: Gérer les stratégies de canal dans Microsoft Teams
author: MikePlumleyMSFT
ms.author: mikeplum
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
ms.localizationpriority: medium
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
- chat-teams-channels-revamp
description: Découvrez comment utiliser et gérer des stratégies de canal d’équipe dans votre organisation pour contrôler ce que les utilisateurs peuvent faire dans les équipes et les canaux.
ms.openlocfilehash: 1223f191550675d5edd7b99a1cf9820fa14c9992
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198556"
---
# <a name="manage-channel-policies-in-microsoft-teams"></a>Gérer les stratégies de canal dans Microsoft Teams

En tant qu’administrateur, vous pouvez utiliser des stratégies dans Microsoft Teams pour contrôler ce que les utilisateurs de votre organisation peuvent faire dans les équipes et les canaux. Par exemple, vous pouvez définir si les utilisateurs sont autorisés à créer des canaux privés ou partagés.

Vous gérez les stratégies teams en accédant à **Stratégies Teams** >  dans le centre d’administration Microsoft Teams. Vous pouvez utiliser la stratégie globale (par défaut à l’échelle de l’organisation) ou créer et attribuer des stratégies personnalisées. Les utilisateurs de votre organisation recevront automatiquement la stratégie globale, sauf si vous créez et leur attribuez une stratégie personnalisée.

Vous pouvez modifier la stratégie globale ou créer et attribuer une stratégie personnalisée. Une fois que vous avez modifié la stratégie globale ou affecté une stratégie, l’application des modifications peut prendre 24 heures.

## <a name="channel-policies"></a>Stratégies de canal

Les stratégies suivantes sont disponibles pour les canaux Teams :

|Stratégie|Description|
|:-----|:----------|
|**Créer des canaux privés**|Lorsque cette option **est activée**, les propriétaires et les membres de l’équipe peuvent créer des canaux privés. (Les propriétaires d’équipe peuvent contrôler si les membres peuvent créer des canaux privés dans chaque équipe.)|
|**Créer des canaux partagés**|Lorsque cette option **est activée**, les propriétaires d’équipe peuvent créer des canaux partagés. Les applications Teams disponibles pour votre organisation sont également disponibles dans des canaux partagés.|
|**Inviter des utilisateurs externes à des canaux partagés**|Lorsque cette option est **activée**, les propriétaires et les membres des canaux partagés peuvent inviter des participants externes à partir d’organisations où une approbation inter-organisations a été configurée. Les stratégies Teams de votre organisation s’appliquent à ces canaux.|
|**Joindre des canaux partagés externes**|Lorsque cette option est **activée**, les utilisateurs peuvent participer à des canaux partagés créés par d’autres organisations où une approbation inter-organisations a été configurée. Les stratégies Teams pour l’autre organisation s’appliquent à ces canaux.|

## <a name="create-a-custom-teams-policy"></a>Créer une stratégie d’équipe personnalisée

1. Dans le volet de navigation gauche du centre d’administration Microsoft Teams, accédez à **Stratégies Teams** > **Teams**.
2. Cliquez sur **Ajouter**.
3. Entrez un nom pour votre stratégie, ainsi qu’une description.

    ![Capture d’écran des paramètres de stratégie teams.](media/teams-policies.png)
4. Activez ou désactivez les paramètres souhaités, puis cliquez sur **Enregistrer**.

5. Cliquez sur **Enregistrer**.

## <a name="edit-a-teams-policy"></a>Modifier une stratégie Teams

Vous pouvez modifier la stratégie globale ou les stratégies personnalisées que vous créez.

1. Dans le volet de navigation gauche du centre d’administration Microsoft Teams, accédez à **Stratégies Teams** > **Teams**.
2. Sélectionnez la stratégie en cliquant à gauche du nom de celle-ci, puis cliquez sur **Modifier**.
3. Activez ou désactivez les paramètres souhaités, puis cliquez sur **Enregistrer**.

## <a name="assign-a-custom-teams-policy-to-users"></a>Affecter une stratégie d’équipe personnalisée aux utilisateurs

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>Rubriques connexes

[Gérer les sites connectés Teams et les sites de canal](/SharePoint/teams-connected-sites)

[Canaux privés dans Teams](private-channels.md)

[Attribuer des stratégies à vos utilisateurs](policy-assignment-overview.md)

[New-CsTeamsChannelsPolicy](/powershell/module/skype/new-csteamschannelspolicy)
