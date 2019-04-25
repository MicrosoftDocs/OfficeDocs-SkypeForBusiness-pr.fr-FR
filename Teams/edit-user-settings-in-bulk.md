---
title: Modifier les paramètres d’utilisateurs Microsoft Teams en bloc
author: LanaChin
ms.author: v-lanac
ms.reviewer: jastark
manager: serdars
ms.date: 04/19/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Découvrez comment gérer les paramètres utilisateur de Microsoft Teams en bloc dans le centre d’administration Microsoft Teams.
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.bulkoperations.edit
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4c1dfba0bdaec642b0ea078d7f10ba022c8514da
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32245065"
---
# <a name="edit-microsoft-teams-user-settings-in-bulk"></a>Modifier les paramètres utilisateur de Microsoft Teams en bloc

En tant qu’administrateur, gérer les paramètres utilisateur d’équipes dans le centre d’administration Microsoft Teams. Dans la page **utilisateurs** , vous pouvez afficher les informations de compte et les détails de licence et modifier les paramètres de stratégie et autres. Vous pouvez modifier les paramètres pour les utilisateurs individuellement ou pour plusieurs utilisateurs en même temps.

## <a name="edit-user-settings-in-bulk"></a>Modifier les paramètres utilisateur en bloc

Utiliser le centre d’administration Microsoft Teams pour modifier les paramètres pour plusieurs utilisateurs à la fois. Nous vous recommandons de modification des paramètres pour les utilisateurs de 20 à la fois. Pour modifier les paramètres pour un grand nombre d’utilisateurs, utilisez PowerShell. Pour plus d’informations, voir [Vue d’ensemble de PowerShell équipes](teams-powershell-overview.md).

1. Dans la navigation de gauche du centre d’administration Microsoft Teams, sélectionnez **les utilisateurs**.
2. Recherche pour les utilisateurs que vous souhaitez modifier ou filtrer l’affichage pour afficher les utilisateurs à modifier.
3. Dans la **& #x 2713 ;** colonne (case à cocher), sélectionnez les utilisateurs en effectuant l’une des options suivantes :
    - Sélectionnez les utilisateurs un à la fois. Un **& #x 2713 ;** s’affiche en regard de chaque utilisateur que vous sélectionnez. Si vous sélectionnez plus de 20 utilisateurs, vous ne sera pas bloqué, mais n’oubliez pas que les utilisateurs plus que vous sélectionnez, prend plus de temps pour effectuer l’opération.

        ![Capture d’écran de la page utilisateurs affichant la sélection de l’utilisateur](media/bulk-edit-user-settings-select-users.png)

    - Cliquez sur le & #x 2713 ; (coche) en haut de la table pour sélectionner tous les utilisateurs (jusqu'à un maximum de 20 utilisateurs), puis cliquez sur **Continuer sélectionner tout** pour terminer la sélection dans la boîte de dialogue **limiter la sélection** .

        ![Capture d’écran de la page utilisateurs, en affichant la limite de sélection](media/bulk-edit-user-settings-select-all-limit.png) <br> Un **& #x 2713 ;** s’affiche en regard des utilisateurs sélectionnés.

        ![Capture d’écran de la page utilisateurs, en affichant les 20 utilisateurs sélectionnés](media/bulk-edit-user-settings-select-all.png)
4. Cliquez sur **Modifier les paramètres**, apportez les modifications souhaitées, puis cliquez sur **Enregistrer**.

    ![Capture d’écran du volet Modifier les paramètres](media/bulk-edit-user-settings-edit-settings.png)
