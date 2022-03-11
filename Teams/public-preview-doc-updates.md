---
title: Préversion publique de Microsoft Teams
author: SerdarSoysal
ms.author: serdars
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
ms.localizationpriority: high
ms.openlocfilehash: 3c07244e49d0c61986ae6eb2c9c9d8e1f522e37b
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62417327"
---
# <a name="microsoft-teams-public-preview"></a>Préversion publique de Microsoft Teams

> [!NOTE] 
> Les fonctionnalités incluses dans la préversion ne seront peut-être pas complètes et risquent de subir des modifications avant d’être disponibles dans la version publique. Nous les proposons uniquement à des fins d’évaluation et d’exploration. Les fonctionnalités dans la préversion ne sont pas prises en charge dans le Cloud de la communauté du secteur public (GCC) Office 365.

La préversion publique de Microsoft Teams vous permet d’accéder en avant-première aux fonctionnalités non publiées de Teams. Les préversions vous permettent d’explorer, puis de tester les fonctionnalités à venir. Nous vous invitons également à nous faire part de vos commentaires sur les fonctionnalités des préversions publiques. La préversion publique est activée pour chaque utilisateur de Teams. Vous n’avez donc pas besoin de vous soucier de l’ensemble de votre organisation.

Pour obtenir la liste de ce qui est disponible dans la préversion publique de Teams, visitez [Notes techniques de la préversion publique de Microsoft Teams](https://techcommunity.microsoft.com/t5/microsoft-teams-public-preview/bd-p/MicrosoftTeamsPublicPreview), [Notes de publication pour les fonctionnalités Microsoft Teams administrateur](/OfficeUpdates/teams-admin) et [Nouveautés dans Teams](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de).

## <a name="set-the-update-policy"></a>Définir la stratégie de mise à jour

Nous avons activé la préversion publique par utilisateur, et une stratégie d’administration permet de contrôler l’option d’activation de cette préversion. Les stratégies de mise à jour permettent de gérer les utilisateurs des préversions de Teams et d’Office qui auront accès aux fonctionnalités d’avant-publication ou de préversion dans l’application Teams. Vous pouvez utiliser et personnaliser la stratégie globale (par défaut à l’échelle de l’organisation), ou créer une ou plusieurs stratégies personnalisées pour vos utilisateurs.

1. Se connecter au [Centre d’administration de Microsoft Teams](https://admin.teams.microsoft.com/).

2. Sélectionnez **Teams** >  **Stratégies de mise à jour de Teams**.

1. Sélectionnez **Ajouter** pour créer une stratégie ou sélectionnez une stratégie existante pour ouvrir **Stratégie de mise à jour**.

2. Nommez la stratégie de mise à jour, ajoutez une description, puis sélectionnez le paramètre pour **Afficher les fonctionnalités en préversion**.

   -   **Suivre la préversion d’Office** (par défaut) : cette nouvelle option activera automatiquement les fonctionnalités de la préversion publique de Teams pour tous les utilisateurs inscrits dans le Canal actuel (préversion) d’Office.Il n’y a plus d’actions requises par l’utilisateur.
   -   **Activé** : cette option active la préversion publique de Teams, que l’utilisateur soit inscrit dans le Canal actuel (préversion) d’office ou non. L’utilisateur final peut également choisir de participer à la préversion publique de Teams dans leur application Teams.

   > [!NOTE]  
   > Pour les utilisateurs existants dans la préversion publique de Teams qui ne sont PAS dans le **Canal actuel (préversion)**, les administrateurs informatiques doivent passer de l’option par défaut **Suivre la préversion d’Office** à **Activé**.
 
   - **Non activé** : les fonctionnalités de la préversion publique de Teams ne sont pas disponibles pour les utilisateurs finaux.

    ![affiche la boîte de dialogue des paramètres de la préversion.](media/public-preview-policy.png)  

Vous pouvez également définir la stratégie à l’aide du cmdlet `Set-CsTeamsUpdateManagementPolicy` PowerShell avec le paramètre `-AllowPublicPreview`.

> [!NOTE]   
> Le paramètre AllowPreview sera prochainement déconseillé.

## <a name="enable-public-preview"></a>Activer la préversion publique

Pour activer la préversion publique sur un client de bureau ou web, vous devez terminer les tâches suivantes :

1. Sélectionnez les trois points à gauche de votre profil pour afficher le menu Teams.
2. Sélectionnez **À propos** > **Préversion publique**.
3. Sélectionnez **Basculer vers la préversion publique**.

> [!NOTE]  
> Cette option est uniquement disponible lorsque l’option **Afficher les fonctionnalités de préversion** est définie sur **Activé**.

## <a name="teams-now-follows-office-preview-users"></a>Teams suit désormais les utilisateurs de la préversion d’Office

La nouvelle stratégie globale par défaut de **Suivre la préversion d’Office** permet aux utilisateurs d’être automatiquement dans le canal actuel (préversion) de Teams s’ils sont dans le Canal actuel (préversion) pour le client Office 365 sur Windows.

Microsoft Office continue de recevoir les mises à jour du Canal actuel (préversion) et le client Teams reçoit les mises à jour via le canal Préversion publique. Cette stratégie ne bascule PAS les canaux d’Office basés sur les canaux Teams. 

**Comment conserver vos utilisateurs existants de la préversion Teams qui n’utilisent PAS le Canal actuel (préversion) d’Office ?**

Pour les utilisateurs existants que vous avez autorisés à s’inscrire ou se désinscrire de la Préversion publique de Teams et si vous souhaitez maintenir ce paramètre dans sa forme actuelle, vous devez basculer de la valeur par défaut **Suivre la préversion d’Office** sur **Activé** (référez-vous à [Définir la stratégie de mise à jour](#set-the-update-policy))

**Comment de désinscrire de ce paramètre ?**

Vous pouvez désactiver le paramètre à partir du Centre d'administration Teams de **Suivre la préversion d’Office** sur **Non activé** (référez-vous à [Définir la stratégie de mise à jour](#set-the-update-policy))

## <a name="known-issues"></a>Problèmes connus

Les utilisateurs du Canal actuel (préversion) d’Office peuvent quitter la Préversion publique de Teams via le menu À propos du client Teams lorsque leur stratégie de mise à jour est définie sur **Suivre la préversion d’Office**. Cette fonctionnalité n’est pas prévue et sera supprimée dans le futur. Le client Teams peut automatiquement repasser sur la Préversion publique lorsque l’appareil est inactif la prochaine fois que l’utilisateur est dans le Canal actuel (préversion) pour Office.

## <a name="related-topics"></a>Voir aussi

[Préversion publique pour les développeurs](/microsoftteams/platform/resources/dev-preview/developer-preview-intro)
