---
title: Gérer la transition de Teams vers le nouveau Centre d’administration Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
description: Découvrez comment gérer les paramètres à l’échelle du client et de l’utilisateur pour Teams pendant la transition de Teams dans le Centre d’administration Microsoft 365 vers le nouveau Centre d’administration Teams.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- ms.teamsadmincenter.dashboard.helparticle.manageteamsnewadmincenter
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
- Skype for Business Online
ms.openlocfilehash: ee63c3d49a8c4b4bf047f0df3910bec39a4d5541
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790416"
---
<a name="manage-teams-during-the-transition-to-the-new-microsoft-teams-admin-center"></a>Gérer Teams lors de la transition vers le nouveau Centre d’administration de Microsoft Teams
======================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

## <a name="what-is-the-new-microsoft-teams-admin-center"></a>Qu’est-ce que le nouveau Centre d’administration Microsoft Teams ?  

La nouvelle expérience du Centre d’administration vous fournira une expérience unifiée pour gérer Teams et Skype Entreprise. Nous vous fournirons des fonctionnalités supplémentaires, des informations de bout en bout et la possibilité de gérer les paramètres Teams au niveau de l’utilisateur.

![Capture d’écran du Centre d’administration Microsoft Teams.](media/manage-teams-skype-for-business-admin-center-portal.png)

## <a name="settings-migrated-to-the-new-microsoft-teams-admin-center"></a>Paramètres migrés vers le nouveau Centre d’administration Microsoft Teams

Le tableau suivant identifie les sections de l’expérience Teams qui ont été migrées et indique la relation entre les paramètres actuels et les stratégies dans le nouveau portail d’administration.

|Section de Teams dans le Centre d’administration Microsoft 365  |Nom du paramètre (niveau client)  |Politique du Centre d’administration Microsoft Teams   |Niveau : Client ou Utilisateur   |
|---------|---------|---------|---------|
|Général     |Afficher l’organigramme dans le profil personnel        |  [TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)       |  Client       |
|Général     |Utiliser Skype Entreprise pour les destinataires qui n’ont pas Teams         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Client         |
|Intégration de courrier électronique     |Autoriser les utilisateurs à envoyer des messages électroniques aux canaux         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Client         |
|Intégration de courrier électronique     |Autoriser la liste des expéditeurs         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)        |Client         |
|Stockage cloud personnalisé     |Box         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Client         |
|Stockage cloud personnalisé     |Dropbox        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Client         |
|Stockage cloud personnalisé     |Egnyte        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Client         |
|Stockage cloud personnalisé     |Google Drive        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Client         |
|Stockage cloud personnalisé     |ShareFile        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Client         |
|Paramètres par type d’utilisateur/licence     |Activer ou désactiver Microsoft Teams pour tous les utilisateurs          |Deprecated<sup>1</sup>        |         |
|Équipes et canaux     |         |Redirige vers Azure Active Directory Group Management (même que l’expérience actuelle).              |Utilisateur         |
|Équipes et canaux     |         |Redirige vers la gestion de groupe AAD (identique à l’expérience actuelle).             |Utilisateur          |
|Applications|Activer les applications externes nouvelles par défaut|Paramètres de l’application à l’échelle de l’organisation|Client|
|Applications|Autoriser les applications externes|Paramètres de l’application à l’échelle de l’organisation|Client|
|Applications|Autoriser le chargement d’applications externes<sup>2</sup>|[TeamsAppSetupPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps)|Utilisateur|
|Applications|Applications par défaut<sup>3</sup>|TeamsAppPermissionPolicy|Utilisateur|
|Applications|Applications externes<sup>3</sup>|TeamsAppPermissionPolicy|Utilisateur|
|Appels et réunions     |Autoriser la planification de réunions privées         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Utilisateur          |
|Appels et réunions     |Autoriser la rencontre de canal ad hoc         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Utilisateur          |
|Appels et réunions     |Autoriser la planification de réunions de canal         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Utilisateur          |
|Appels et réunions     |Autoriser les vidéos pendant les réunions         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Utilisateur          |
|Appels et réunions     |Autoriser le partage d’écran dans les réunions         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Utilisateur          |
|Appels et réunions     |Autoriser les appels privés         |[TeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)        |Utilisateur          |
|Messagerie     |Activer Giphy pour permettre aux utilisateurs d’ajouter des GIF aux conversations         |[TeamsMesspolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Utilisateur         |
|Messagerie     |Évaluation du contenu         |[TeamsMesspolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Utilisateur         |
|Messagerie     |Activer les mèmes que les utilisateurs peuvent modifier et ajouter aux conversations         |[TeamsMesspolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Utilisateur         |
|Messagerie     |Activer les autocollants que les utilisateurs peuvent modifier et ajouter aux conversations         |[TeamsMesspolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Utilisateur         |
|Messagerie     |Autoriser les propriétaires à supprimer tous les messages         |[TeamsMesspolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Utilisateur         |
|Messagerie     |Autoriser les utilisateurs à modifier leurs propres messages         |[TeamsMesspolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Utilisateur         |
|Messagerie     |Autoriser les utilisateurs à supprimer leurs propres messages         |[TeamsMesspolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Utilisateur         |
|Messagerie     |Permet aux utilisateurs de discuter en privé         |[TeamsMesspolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Utilisateur         |

<sup>1</sup> Deprecated for Guest. L’activation ou la désactivation de l’invité peut désormais être gérée dans le Centre d’administration Microsoft Teams. L’activation ou la désactivation de Teams pour les entreprises , les étudiants pour l’éducation et les enseignants seront bientôt désactivés. Pour ce faire, vous devez affecter des licences dans le Centre d’administration Microsoft 365. Voir [Gérer l’accès des utilisateurs à Microsoft Teams.](user-access.md)
<br><br>
<sup>2 Le</sup> chargement débordage est fractioné comme suit :

- Autoriser un utilisateur à télécharger une version d’application qui peut être gérée au niveau de l’utilisateur [dans TeamsAppSetupPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps)
- Autorisez les utilisateurs d’un client à interagir avec des applications personnalisées qui peuvent être gérées au niveau du client dans les paramètres d’application à l’échelle de l’organisation.

<sup>3 Les</sup> applications et applications externes par défaut peuvent être activées et désactivées au niveau de l’utilisateur dans TeamsAppPermissionPolicy. En outre, les applications peuvent être bloquées au niveau du client dans les paramètres d’application à l’échelle de l’organisation qui remplacent tous les paramètres utilisateur et client.

> [!NOTE]
> Vous continuerez à utiliser le tableau de bord Groupes dans le Centre d’administration Microsoft 365 pour la configuration des équipes et des canaux. Les paramètres des applications restent dans la zone Teams du Centre d’administration Microsoft 365 et sont migrés ultérieurement.

## <a name="manage-settings-during-the-migration"></a>Gérer les paramètres pendant la migration

Vous pouvez continuer à modifier les paramètres dans le Centre d’administration Microsoft 365 et le Centre d’administration Skype Entreprise jusqu’à ce que la migration d’une section soit terminée pour votre client.

Le tableau suivant indique où vous pouvez gérer les fonctionnalités pendant la migration.

|Fonctionnalité  |Centre d’administration Microsoft Teams                      |Centre d’administration Skype Entreprise (hérité)  |Centre d’administration Microsoft 365  |
|---------|:---------:|:---------:|:---------:|
|Stratégies de messagerie, de réunions et d’événements en direct Teams     |     X    |         |         |
|Stratégie de mise à niveau de Teams     |    X     |         |         |
|Paramètres invités pour la messagerie, les réunions et la voix     |   X      |         |         |
|Gestion du cycle de vie Teams   |    X    |      |       |
|Paramètres teams   |    X    |      |       |
|Paramètres d’accès externe     |    X    |      |       |
|Gestion des utilisateurs    |         |         |    X     |
|Audioconférence     |    X     |    X     |         |
|Forfaits d'appels     |    X    |    X     |         |
|Système téléphonique    |    X    |     X    |         |
|Gestion des numéros de téléphone     |    X    |   X      |         |
|Licences pour les fonctionnalités vocales dans le cloud     |         |         |    X     |
|Les standards automatiques     |    X    |          |         |
|Files d'attente des appels     |    X    |          |         |

## <a name="manage-settings-after-the-migration"></a>Gérer les paramètres après la migration

Une fois la migration de ces paramètres terminée, nous les désactivons dans le Centre d’administration Microsoft 365 et dans le Centre d’administration Skype Entreprise. Ils peuvent ensuite être gérés dans le nouveau Centre d’administration Microsoft Teams.
