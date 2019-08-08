---
title: Modifier les paramètres d’utilisateurs Microsoft Teams en bloc
author: LanaChin
ms.author: v-lanac
ms.reviewer: jastark
manager: serdars
ms.date: 04/19/2019
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Découvrez comment gérer les paramètres utilisateur de Microsoft teams en bloc dans le centre d’administration Microsoft Teams.
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.bulkoperations.edit
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9585266ff2af124a1b9985c4cf18d842bc45af5c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236780"
---
# <a name="edit-microsoft-teams-user-settings-in-bulk"></a>Modification des paramètres utilisateur de Microsoft teams en bloc

En tant qu’administrateur, vous pouvez gérer les paramètres utilisateur de teams dans le centre d’administration Microsoft Teams. Dans la page **utilisateurs** , vous pouvez afficher des informations telles que les détails du compte et de la licence, ainsi que la stratégie d’édition et d’autres paramètres. Vous pouvez modifier les paramètres pour les utilisateurs individuellement ou pour plusieurs utilisateurs en même temps.

## <a name="edit-user-settings-in-bulk"></a>Modification des paramètres utilisateur en bloc

Utilisez le centre d’administration de Microsoft teams pour modifier les paramètres de plusieurs utilisateurs à la fois. Nous vous recommandons de modifier les paramètres de 20 utilisateurs à la fois. Pour modifier les paramètres d’un grand nombre d’utilisateurs, utilisez PowerShell. Pour plus d’informations, voir [vue d’ensemble de PowerShell teams](teams-powershell-overview.md).

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, sélectionnez **utilisateurs**.
2. Recherchez les utilisateurs que vous souhaitez modifier ou filtrez l’affichage pour afficher les utilisateurs que vous voulez modifier.
3. Dans la colonne **&#x2713;** (coche), sélectionnez les utilisateurs en effectuant l’une des opérations suivantes:
    - Sélectionner des utilisateurs un par un. Un **&#x2713;** est affiché en regard de chaque utilisateur que vous sélectionnez. Si vous sélectionnez plus de 20 utilisateurs, vous ne serez pas bloqué, mais n’oubliez pas que plus le nombre d’utilisateurs que vous sélectionnez est long, plus l’opération sera terminée.

        ![Capture d’écran de la page utilisateurs montrant la sélection de l’utilisateur](media/bulk-edit-user-settings-select-users.png)

    - Cliquez sur la &#x2713; (coche) en haut du tableau pour sélectionner tous les utilisateurs (jusqu’à 20 utilisateurs maximum), puis dans la boîte de dialogue **limiter la sélection** , cliquez sur **Continuer tout sélectionner** pour terminer la sélection.

        ![Capture d’écran de la page utilisateurs montrant la limite de sélection](media/bulk-edit-user-settings-select-all-limit.png) <br> Un **&#x2713;** est affiché en regard des utilisateurs sélectionnés.

        ![Capture d’écran de la page utilisateurs montrant 20 utilisateurs sélectionnés](media/bulk-edit-user-settings-select-all.png)
4. Cliquez sur **modifier les paramètres**, apportez les modifications souhaitées, puis cliquez sur **Enregistrer**.

    ![Capture d’écran du volet modifier les paramètres](media/bulk-edit-user-settings-edit-settings.png)
