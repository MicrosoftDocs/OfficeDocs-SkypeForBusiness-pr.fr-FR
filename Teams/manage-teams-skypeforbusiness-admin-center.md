---
title: Gérer Teams transition vers le nouveau centre d’administration Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: ''
ROBOTS: NOINDEX, NOFOLLOW
description: Découvrez comment gérer les paramètres utilisateur et à l’échelle du client pour Teams pendant la transition de Teams dans le Centre d'administration Microsoft 365 au nouveau centre d’administration Teams.
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
ms.openlocfilehash: 83b65724099aa46bfe1f1719430e70d8da86ce33
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675086"
---
# <a name="manage-teams-during-the-transition-to-the-new-microsoft-teams-admin-center"></a>Gérer Teams lors de la transition vers le nouveau Centre d’administration de Microsoft Teams

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

## <a name="what-is-the-new-microsoft-teams-admin-center"></a>Qu’est-ce que le nouveau centre d’administration Microsoft Teams ?  

La nouvelle expérience du Centre d’administration vous fournira une expérience unifiée pour gérer les Teams et les Skype Entreprise. Nous proposons des fonctionnalités supplémentaires, des insights de bout en bout et la possibilité de gérer Teams paramètres au niveau de l’utilisateur.

![Capture d’écran du centre d’administration Microsoft Teams.](media/manage-teams-skype-for-business-admin-center-portal.png)

## <a name="settings-migrated-to-the-new-microsoft-teams-admin-center"></a>Paramètres migré vers le nouveau centre d’administration Microsoft Teams

Le tableau suivant identifie les sections de l’expérience de Teams qui ont été migrées et montre la relation entre les paramètres actuels et les stratégies dans le nouveau portail d’administration.

|Section de Teams dans Centre d'administration Microsoft 365  |Nom du paramètre (niveau locataire)  |Microsoft Teams stratégie du centre d’administration   |Niveau : locataire ou utilisateur   |
|---------|---------|---------|---------|
|Général     |Afficher le graphique organisationnel dans un profil personnel        |  [TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)       |  Locataire       |
|Général     |Utilisez Skype Entreprise pour les destinataires qui n’ont pas de Teams         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Locataire         |
|Intégration de courrier électronique     |Autoriser les utilisateurs à envoyer des e-mails aux canaux         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Locataire         |
|Intégration de courrier électronique     |Autoriser la liste des expéditeurs         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)        |Locataire         |
|Stockage cloud personnalisé     |Boîte         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Locataire         |
|Stockage cloud personnalisé     |Dropbox        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Locataire         |
|Stockage cloud personnalisé     |Egnyte        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Locataire         |
|Stockage cloud personnalisé     |Google Drive        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Locataire         |
|Stockage cloud personnalisé     |ShareFile        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Locataire         |
|Paramètres par type d’utilisateur/licence     |Activer ou désactiver Microsoft Teams pour tous les utilisateurs          |Déprécié<sup>1</sup>        |         |
|Équipes et canaux     |         |Redirige vers Azure Active Directory gestion de groupe (identique à l’expérience actuelle).              |Utilisateur         |
|Équipes et canaux     |         |Redirige vers la gestion de groupe AAD (identique à l’expérience actuelle).             |Utilisateur          |
|Applications|Activer les applications externes nouvelles par défaut|Paramètres de l’application à l’échelle de l’organisation|Locataire|
|Applications|Autoriser les applications externes|Paramètres de l’application à l’échelle de l’organisation|Locataire|
|Applications|Autoriser le chargement indépendant des applications externes<sup>2</sup>|[TeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy)|Utilisateur|
|Applications|Applications par défaut<sup>3</sup>|TeamsAppPermissionPolicy|Utilisateur|
|Applications|Applications externes<sup>3</sup>|TeamsAppPermissionPolicy|Utilisateur|
|Appels et réunions     |Autoriser la planification de réunions privées         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |Utilisateur          |
|Appels et réunions     |Autoriser la réunion de canal ad hoc         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |Utilisateur          |
|Appels et réunions     |Autoriser la planification de réunions de canal         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |Utilisateur          |
|Appels et réunions     |Autoriser les vidéos dans les réunions         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |Utilisateur          |
|Appels et réunions     |Autoriser le partage d’écran dans les réunions         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |Utilisateur          |
|Appels et réunions     |Autoriser les appels privés         |[TeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)        |Utilisateur          |
|Messagerie     |Activer Giphy pour permettre aux utilisateurs d’ajouter des GIF aux conversations         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Utilisateur         |
|Messagerie     |Évaluation du contenu         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Utilisateur         |
|Messagerie     |Activer les mèmes que les utilisateurs peuvent modifier et ajouter aux conversations         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Utilisateur         |
|Messagerie     |Activer les autocollants que les utilisateurs peuvent modifier et ajouter aux conversations         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Utilisateur         |
|Messagerie     |Autoriser les propriétaires à supprimer tous les messages         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Utilisateur         |
|Messagerie     |Autoriser les utilisateurs à modifier leurs propres messages         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Utilisateur         |
|Messagerie     |Autoriser les utilisateurs à supprimer leurs propres messages         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Utilisateur         |
|Messagerie     |Permet aux utilisateurs de discuter en privé         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Utilisateur         |

<sup>1</sup> Déconseillé pour l’invité. L’activation/désactivation de l’invité peut désormais être gérée dans le centre d’administration Microsoft Teams. L’activation/désactivation de Teams pour les Enterprise d’entreprise, Edu Student et Edu Faculty sera bientôt déconseillée. Cela doit être géré en attribuant des licences dans le Centre d'administration Microsoft 365. Consultez [Gérer l’accès utilisateur à Microsoft Teams](user-access.md).
<br><br>
<sup>2</sup> Le chargement indépendant est fractionné comme suit :

- Autoriser un utilisateur à charger des applications qui peuvent être gérées au niveau de l’utilisateur dans [TeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy).
- Permettre aux utilisateurs d’un locataire d’interagir avec des applications personnalisées qui peuvent être gérées au niveau du locataire dans les paramètres d’application à l’échelle de l’organisation.

<sup>3 Les</sup> applications par défaut et les applications externes peuvent être activées et désactivées au niveau de l’utilisateur dans TeamsAppPermissionPolicy. En outre, les applications peuvent être bloquées au niveau du locataire dans les paramètres d’application à l’échelle de l’organisation, ce qui remplace tous les paramètres au niveau de l’utilisateur et du locataire.

> [!NOTE]
> Vous continuerez à utiliser le tableau de bord Groupes dans le Centre d'administration Microsoft 365 pour la configuration liée aux Teams et aux canaux. Paramètres for Apps restera dans la zone Teams du Centre d'administration Microsoft 365 et sera migré ultérieurement.

## <a name="manage-settings-during-the-migration"></a>Gérer les paramètres pendant la migration

Vous pouvez continuer à modifier les paramètres du Centre d'administration Microsoft 365 et du centre d’administration Skype Entreprise jusqu’à ce que la migration d’une section soit terminée pour votre locataire.

Le tableau suivant indique où vous pouvez gérer les fonctionnalités pendant la migration.

|Fonctionnalité  |centre d’administration Microsoft Teams                      |centre d’administration Skype Entreprise (hérité)  |Centre d'administration Microsoft 365  |
|---------|:---------:|:---------:|:---------:|
|Teams stratégies de messagerie, de réunions et d’événements en direct     |     X    |         |         |
|stratégie de mise à niveau Teams     |    X     |         |         |
|Paramètres invités pour la messagerie, les réunions et la voix     |   X      |         |         |
|gestion du cycle de vie Teams   |    X    |      |       |
|Teams Paramètres   |    X    |      |       |
|Paramètres d’accès externe     |    X    |      |       |
|Gestion des utilisateurs    |         |         |    X     |
|Audioconférence     |    X     |    X     |         |
|Forfaits d'appels     |    X    |    X     |         |
|Système téléphonique    |    X    |     X    |         |
|gestion des nombres Téléphone     |    X    |   X      |         |
|Licences pour les fonctionnalités vocales cloud     |         |         |    X     |
|Les standards automatiques     |    X    |          |         |
|Files d'attente des appels     |    X    |          |         |

## <a name="manage-settings-after-the-migration"></a>Gérer les paramètres après la migration

Une fois la migration de ces paramètres terminée, nous les désactivons dans le Centre d'administration Microsoft 365 et le centre d’administration Skype Entreprise, et ils peuvent ensuite être gérés dans le nouveau centre d’administration Microsoft Teams.
