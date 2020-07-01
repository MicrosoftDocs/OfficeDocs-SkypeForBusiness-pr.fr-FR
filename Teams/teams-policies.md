---
title: Gérer les stratégies d’équipes dans Microsoft teams
author: lanachin
ms.author: v-lanac
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
description: Découvrez comment utiliser et gérer les stratégies d’équipe dans votre organisation pour contrôler ce que les utilisateurs peuvent faire dans les équipes et les canaux.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
ms.openlocfilehash: 9ed0bd3aadcde76835bb3d435429785ceaf562a2
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938143"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a>Gérer les stratégies d’équipes dans Microsoft teams

En tant qu’administrateur, vous pouvez utiliser les stratégies d’équipe de Microsoft teams pour contrôler ce que peuvent faire les utilisateurs de votre organisation dans les équipes et les canaux. Par exemple, vous pouvez définir si les utilisateurs sont autorisés à découvrir des équipes privées dans les résultats de la recherche et dans la Galerie d’équipes et si les utilisateurs sont autorisés à créer des canaux privés.

Pour gérer les stratégies d’équipe, **accédez à stratégies teams teams**  >  **Teams policies** dans le centre d’administration Microsoft Teams. Vous pouvez utiliser la stratégie globale par défaut de l’organisation ou créer et attribuer des stratégies personnalisées. Les utilisateurs de votre organisation recevront automatiquement la stratégie globale, sauf si vous créez et leur attribuez une stratégie personnalisée.

Vous pouvez modifier la stratégie globale ou créer et attribuer une stratégie personnalisée. Après avoir modifié la stratégie globale ou affecté une stratégie, plusieurs heures peuvent être nécessaires pour que les modifications prennent effet.

## <a name="create-a-custom-teams-policy"></a>Créer une stratégie d’équipe personnalisée

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, **accédez à**  >  **stratégies teams**.
2. Cliquez sur **Ajouter**.
3. Entrez un nom pour votre stratégie, ainsi qu’une description.

    ![Capture d’écran des paramètres de stratégie d’équipe](media/teams-policies.png)
4. Choisissez les paramètres de votre choix :

- **Découvrez les équipes privées** (en préversion<a name="discoverteams"> </a> privée) : activez ce paramètre pour permettre aux utilisateurs de découvrir les équipes privées dans les résultats de la recherche et dans la Galerie d’équipe.
- **Créer des canaux privés**: <a name="createchannels"> </a>activez ce paramètre pour autoriser les utilisateurs à créer des canaux privés.

5. Cliquez sur **Enregistrer**.

## <a name="edit-a-teams-policy"></a>Modifier une stratégie d’équipe

Vous pouvez modifier la stratégie globale ou toutes les stratégies personnalisées que vous créez.

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, **accédez à**  >  **stratégies teams**.
2. Sélectionnez la stratégie en cliquant à gauche du nom de la stratégie, puis cliquez sur **modifier**.
3. Activez ou désactivez les paramètres souhaités, puis cliquez sur **Enregistrer**.

## <a name="assign-a-custom-teams-policy-to-users"></a>Attribuer une stratégie d’équipe personnalisée aux utilisateurs

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>Sujets associés

[Gérer la découverte des équipes privées dans Teams](manage-discovery-of-private-teams.md)

[Canaux privés dans teams](private-channels.md)

[Attribuer des stratégies à vos utilisateurs dans teams](assign-policies.md)
