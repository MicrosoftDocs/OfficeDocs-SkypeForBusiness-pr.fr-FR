---
title: Préversion publique de Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: dansteve
search.appverid: MET150
f1.keywords:
- NOCSH
description: En savoir plus sur la préversion publique dans Microsoft Teams. Essayez les nouvelles fonctionnalités, puis envoyez vos commentaires.
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: e2724901a2a1b534053e2145da442e989aed4e6c
ms.sourcegitcommit: b39bd1de0219a9e3a3b0c97fc485c9578ddb643c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2021
ms.locfileid: "53230541"
---
# <a name="microsoft-teams-public-preview"></a>Préversion publique de Microsoft Teams

> [!NOTE]
> Les fonctionnalités incluses dans la préversion ne seront peut-être pas complètes et risquent de subir des modifications avant d’être disponibles dans la version publique. Nous les proposons uniquement à des fins d’évaluation et d’exploration. Non pris en charge dans le cloud communautaire pour le secteur public Office 365 (GCC).

La préversion publique de Microsoft Teams vous permet d’accéder en avant-première aux fonctionnalités non publiées de Teams. Les préversions vous permettent d’explorer, puis de tester les fonctionnalités à venir. Nous vous invitons également à nous faire part de vos commentaires sur les fonctionnalités des préversions publiques. La préversion publique est activée pour chaque utilisateur de Teams. Vous n’avez donc pas besoin de vous soucier de l’ensemble de votre organisation.

Pour obtenir la liste des ressources disponibles dans la prévisualisation publique Teams, veuillez consulter la rubrique [Notes de publication pour le canal actuel d’Office (Preview)](/officeupdates/current-channel-preview).

## <a name="set-the-update-policy"></a>Définir la stratégie de mise à jour

Nous avons activé la préversion publique par utilisateur, et une stratégie d’administration permet de contrôler l’option d’activation de cette préversion. Les stratégies de mise à jour permettent de gérer les utilisateurs des préversions de Teams et d’Office qui auront accès aux fonctionnalités d’avant-publication ou de préversion dans l’application Teams. Vous pouvez utiliser et personnaliser la stratégie globale (par défaut à l’échelle de l’organisation), ou créer une ou plusieurs stratégies personnalisées pour vos utilisateurs.

1. Connectez-vous au centre d'administration.
2. Sélectionnez **Teams**>**Stratégies de mise à jour**.

   ![Sélectionner l’option Stratégies de mise à jour](media/updatePolicies.png)

3. Sélectionnez **Ajouter**.
4. Nommez la stratégie de mise à jour, ajoutez une description, puis activez **Afficher les fonctionnalités en préversion**.

Vous pouvez également définir la stratégie à l’aide de PowerShell à l’aide du `Set-CsTeamsUpdateManagementPolicy`cmdlet avec le `-AllowPreview` paramètre booléen.

## <a name="enable-public-preview"></a>Activer la préversion publique

Pour activer la préversion publique sur un client de bureau ou web, effectuez les tâches suivantes :

1. Sélectionnez les trois points à gauche de votre profil pour afficher le menu Teams.
2. Sélectionnez **À propos** > **Préversion publique**.
3. Sélectionnez **Basculer vers la préversion publique**.

## <a name="related-topics"></a>Voir aussi

[Préversion publique pour les développeurs](/microsoftteams/platform/resources/dev-preview/developer-preview-intro)
