---
title: Gérer Teams transition vers le nouveau Centre Teams’administration
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: ''
ROBOTS: NOINDEX, NOFOLLOW
description: Découvrez comment gérer les paramètres à l’échelle du client et des utilisateurs pour Teams lors de la transition de Teams dans le Centre d'administration Microsoft 365 vers le nouveau Teams d’administration.
ms.localizationpriority: medium
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
ms.openlocfilehash: 727aa58f3e7a91336355730ce5f0a552ea09fdc9
ms.sourcegitcommit: b2566e64e02cb51d18836630d3aa9b6f27b924da
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2021
ms.locfileid: "59491734"
---
# <a name="manage-teams-during-the-transition-to-the-new-microsoft-teams-admin-center"></a>Gérer Teams lors de la transition vers le nouveau Centre d’administration de Microsoft Teams

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

## <a name="what-is-the-new-microsoft-teams-admin-center"></a>Nouveautés du Centre d’Microsoft Teams’administration  

La nouvelle expérience du Centre d’administration vous fournira une expérience unifiée pour gérer à la fois les Teams et les Skype Entreprise. Nous vous fournirons des fonctionnalités supplémentaires, des informations de bout en bout et nous avons la possibilité de gérer les paramètres Teams au niveau de l’utilisateur.

![Capture d’écran du Microsoft Teams d’administration.](media/manage-teams-skype-for-business-admin-center-portal.png)

## <a name="settings-migrated-to-the-new-microsoft-teams-admin-center"></a>Paramètres migré vers le nouveau Centre Microsoft Teams’administration

Le tableau suivant identifie les sections de l’expérience Teams qui ont été migrées et indique la relation entre les paramètres actuels et les stratégies dans le nouveau portail d’administration.

|Section des Teams dans Centre d'administration Microsoft 365  |Nom du paramètre (niveau client)  |Microsoft Teams centre d’administration   |Niveau : Client ou Utilisateur   |
|---------|---------|---------|---------|
|Général     |Afficher l’organigramme dans le profil personnel        |  [TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)       |  Client       |
|Général     |Utilisez Skype Entreprise pour les destinataires qui ne l’ont pas Teams         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Client         |
|Intégration de courrier électronique     |Autoriser les utilisateurs à envoyer des messages électroniques aux canaux         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Client         |
|Intégration de courrier électronique     |Autoriser la liste des expéditeurs         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)        |Client         |
|Stockage cloud personnalisé     |Box         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Client         |
|Stockage cloud personnalisé     |Dropbox        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Client         |
|Stockage cloud personnalisé     |Egnyte        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Client         |
|Stockage cloud personnalisé     |Google Drive        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Client         |
|Stockage cloud personnalisé     |ShareFile        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Client         |
|Paramètres par type d’utilisateur/licence     |Activer Microsoft Teams ou désactiver l’Microsoft Teams pour tous les utilisateurs          |Deprecated<sup>1</sup>        |         |
|Équipes et canaux     |         |Redirige vers Azure Active Directory gestion des groupes (même que l’expérience actuelle).              |Utilisateur         |
|Équipes et canaux     |         |Redirige vers la gestion de groupe AAD (identique à l’expérience actuelle).             |Utilisateur          |
|Applications|Activer les applications externes nouvelles par défaut|Paramètres de l’application à l’échelle de l’organisation|Client|
|Applications|Autoriser les applications externes|Paramètres de l’application à l’échelle de l’organisation|Client|
|Applications|Autoriser le chargement d’applications externes<sup>2</sup>|[TeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy)|Utilisateur|
|Applications|Applications par défaut<sup>3</sup>|TeamsAppPermissionPolicy|Utilisateur|
|Applications|Applications externes<sup>3</sup>|TeamsAppPermissionPolicy|Utilisateur|
|Appels et réunions     |Autoriser la planification de réunions privées         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |Utilisateur          |
|Appels et réunions     |Autoriser la rencontre de canal ad hoc         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |Utilisateur          |
|Appels et réunions     |Autoriser la planification de réunions de canal         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |Utilisateur          |
|Appels et réunions     |Autoriser les vidéos pendant les réunions         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |Utilisateur          |
|Appels et réunions     |Autoriser le partage d’écran dans les réunions         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |Utilisateur          |
|Appels et réunions     |Autoriser les appels privés         |[TeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)        |Utilisateur          |
|Messagerie     |Activer Giphy pour permettre aux utilisateurs d’ajouter des GIF aux conversations         |[TeamsMesspolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Utilisateur         |
|Messagerie     |Évaluation du contenu         |[TeamsMesspolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Utilisateur         |
|Messagerie     |Activer les mèmes que les utilisateurs peuvent modifier et ajouter aux conversations         |[TeamsMesspolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Utilisateur         |
|Messagerie     |Activer les autocollants que les utilisateurs peuvent modifier et ajouter aux conversations         |[TeamsMesspolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Utilisateur         |
|Messagerie     |Autoriser les propriétaires à supprimer tous les messages         |[TeamsMesspolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Utilisateur         |
|Messagerie     |Autoriser les utilisateurs à modifier leurs propres messages         |[TeamsMesspolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Utilisateur         |
|Messagerie     |Autoriser les utilisateurs à supprimer leurs propres messages         |[TeamsMesspolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Utilisateur         |
|Messagerie     |Permet aux utilisateurs de discuter en privé         |[TeamsMesspolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Utilisateur         |

<sup>1</sup> Deprecated for Guest. L’activation ou la désactivation de l’invité peut désormais être gérée dans le centre Microsoft Teams’administration. L’activation ou la désactivation Teams pour les Enterprise, l’éducation pour les étudiants et les enseignants de l’éducation seront bientôt désactivées. Pour ce faire, vous devez affecter des licences dans le Centre d'administration Microsoft 365. Voir [Gérer l’accès des utilisateurs à Microsoft Teams.](user-access.md)
<br><br>
<sup>2 Le</sup> chargement débordage est fractioné comme suit :

- Autoriser un utilisateur à télécharger une version d’application qui peut être gérée au niveau de l’utilisateur [dans TeamsAppSetupPolicy.](/powershell/module/skype/set-csteamsappsetuppolicy)
- Autorisez les utilisateurs d’un client à interagir avec des applications personnalisées qui peuvent être gérées au niveau du client dans les paramètres d’application à l’échelle de l’organisation.

<sup>3 Les</sup> applications et applications externes par défaut peuvent être activées et désactivées au niveau de l’utilisateur dans TeamsAppPermissionPolicy. En outre, les applications peuvent être bloquées au niveau du client dans les paramètres d’application à l’échelle de l’organisation qui remplacent tous les paramètres utilisateur et client.

> [!NOTE]
> Vous continuerez à utiliser le tableau de bord Groupes dans le Centre d'administration Microsoft 365 pour la configuration liée aux Teams et aux canaux. Paramètres applications reste dans la zone Teams du Centre d'administration Microsoft 365 et est migré plus tard.

## <a name="manage-settings-during-the-migration"></a>Gérer les paramètres pendant la migration

Vous pouvez continuer à modifier les paramètres du Centre d’administration Centre d'administration Microsoft 365 et Skype Entreprise’administration jusqu’à ce que la migration d’une section soit terminée pour votre client.

Le tableau suivant indique où vous pouvez gérer les fonctionnalités pendant la migration.

|Fonctionnalité  |Microsoft Teams d’administration                      |Skype Entreprise d’administration (hérité)  |Centre d'administration Microsoft 365  |
|---------|:---------:|:---------:|:---------:|
|Teams Stratégies de messagerie, de réunions et d’événements en direct     |     X    |         |         |
|Teams Stratégie de mise à niveau     |    X     |         |         |
|Paramètres invités pour la messagerie, les réunions et la voix     |   X      |         |         |
|Teams Gestion du cycle de vie   |    X    |      |       |
|Teams Paramètres   |    X    |      |       |
|Paramètres d’accès externe     |    X    |      |       |
|Gestion des utilisateurs    |         |         |    X     |
|Audioconférence     |    X     |    X     |         |
|Forfaits d'appels     |    X    |    X     |         |
|Système téléphonique    |    X    |     X    |         |
|Téléphone gestion des nombres     |    X    |   X      |         |
|Licences pour les fonctionnalités vocales dans le cloud     |         |         |    X     |
|Les standards automatiques     |    X    |          |         |
|Files d'attente des appels     |    X    |          |         |

## <a name="manage-settings-after-the-migration"></a>Gérer les paramètres après la migration

Une fois la migration de ces paramètres terminée, nous les désactivons dans le centre d’administration Centre d'administration Microsoft 365 et Skype Entreprise. Ils peuvent ensuite être gérés dans le nouveau Centre d’administration Microsoft Teams.
