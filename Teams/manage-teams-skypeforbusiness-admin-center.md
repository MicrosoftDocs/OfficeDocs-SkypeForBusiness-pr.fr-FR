---
title: Gérer Teams lors de la transition vers le nouveau Centre d’administration de Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
description: Comprendre comment gérer les clients à l’échelle et les paramètres utilisateur pour les équipes pendant la transition entre les équipes expérience dans le centre d’administration Office 365 pour le nouveau centre d’administration de Microsoft Teams.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
f1keywords: ms.teamsadmincenter.dashboard.helparticle.manageteamsnewadmincenter
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
- Skype for Business Online
ms.openlocfilehash: 9f1adb47709d3e053bb2349d8a3e548bedc58d9d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199566"
---
<a name="manage-teams-during-the-transition-to-the-new-microsoft-teams-admin-center"></a>Gérer Teams lors de la transition vers le nouveau Centre d’administration de Microsoft Teams
======================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

## <a name="what-is-the-new-microsoft-teams-admin-center"></a>Quel est le nouveau centre d’administration de Microsoft Teams ?  

La nouvelle expérience du centre d’administration vous fournira une expérience unifiée pour gérer des équipes et Skype pour les entreprises. Offrir des fonctionnalités supplémentaires, détails de bout en bout et la possibilité de gérer les paramètres des équipes sur un niveau de l’utilisateur.

![Capture d’écran du centre d’administration équipes Microsoft.](media/manage-teams-skype-for-business-admin-center-portal.png)

## <a name="settings-migrated-to-the-new-microsoft-teams-admin-center"></a>Paramètres migrés vers le nouveau centre d’administration de Microsoft Teams

Le tableau suivant identifie les sections de l’expérience des équipes qui ont été migrées et indique la relation entre les paramètres et les stratégies dans le nouveau portail d’administration.

|Section d’équipes dans le centre d’administration Office 365  |Nom du paramètre (niveau client)  |Stratégie de centre d’administration Microsoft Teams   |Niveau : Client ou utilisateur   |
|---------|---------|---------|---------|
|Général     |Afficher la conversation d’organisation dans le profil personnel        |  [TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)       |  Client       |
|Général     |Utilisez Skype pour les entreprises pour les destinataires qui ne possèdent pas les équipes         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Client         |
|Intégration de courrier électronique     |Autoriser les utilisateurs à envoyer des messages électroniques à canaux         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Client         |
|Intégration de courrier électronique     |Autoriser les expéditeurs liste         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)        |Client         |
|Stockage cloud personnalisé     |Zone         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Client         |
|Stockage cloud personnalisé     |Échange        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Client         |
|Stockage cloud personnalisé     |Lecteur de Google        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Client         |
|Stockage cloud personnalisé     |ShareFile        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Client         |
|Paramètres par type de licence d’utilisateur     |Activer Microsoft Teams activé ou désactivé pour tous les utilisateurs          |Obsolètes<sup>1</sup>        |         |
|Équipes et canaux     |         |Redirige vers Azure Active Directory groupe Management (identique à l’expérience).              |Utilisateur         |
|Équipes et canaux     |         |Redirige vers la gestion de groupe DAS (identique à l’expérience).             |Utilisateur          |
|Applications|Activer les applications externes nouvelles par défaut|Paramètres d’application à l’échelle de l’organisation|Client|
|Applications|Autoriser les applications externes|Paramètres d’application à l’échelle de l’organisation|Client|
|Applications|Autoriser le chargement de version test des applications externes<sup>2</sup>|[TeamsAppSetupPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps)|Utilisateur|
|Applications|Par défaut applications<sup>3</sup>|TeamsAppPermissionPolicy|Utilisateur|
|Applications|Applications externes<sup>3</sup>|TeamsAppPermissionPolicy|Utilisateur|
|Les réunions et les appels     |Autoriser la planification de réunions privées         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Utilisateur          |
|Les réunions et les appels     |Autoriser les meetup du canal Ad hoc         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Utilisateur          |
|Les réunions et les appels     |Autoriser la planification de réunions de canal         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Utilisateur          |
|Les réunions et les appels     |Autoriser les vidéos de réunions         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Utilisateur          |
|Les réunions et les appels     |Autoriser les réunions de partage d’écran         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Utilisateur          |
|Les réunions et les appels     |Autorise les appels privée         |[TeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)        |Utilisateur          |
|Messagerie      |Activer Giphy afin que les utilisateurs peuvent ajouter des images GIF à des conversations         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Utilisateur         |
|Messagerie      |Évaluation du contenu         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Utilisateur         |
|Messagerie      |Activer les memes que les utilisateurs peuvent modifier et ajouter des conversations         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Utilisateur         |
|Messagerie      |Activer autocollants que les utilisateurs peuvent modifier et ajouter des conversations         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Utilisateur         |
|Messagerie      |Autoriser les propriétaires supprimer tous les messages         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Utilisateur         |
|Messagerie      |Permettre aux utilisateurs de modifier leurs propres messages         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Utilisateur         |
|Messagerie      |Autoriser les utilisateurs à supprimer leurs propres messages         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Utilisateur         |
|Messagerie      |Permet aux utilisateurs de chat privé         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Utilisateur         |

<sup>1</sup> déconseillée pour invité. Activation/désactivation de l’invité peuvent maintenant être géré dans le centre d’administration Microsoft Teams. Activation/désactivation des équipes pour l’entreprise, Edu étudiant, et Université Edu sera bientôt déconseillée. Il doit être gérée par l’attribution de licences dans le centre d’administration d’Office 365. Consultez la rubrique [gérer l’accès utilisateur aux équipes de Microsoft](user-access.md).
<br><br>
<sup>2</sup> chargement de version test est fractionnée comme suit :

- Permettre à un utilisateur pour les applications sideload qui peuvent être gérés à un niveau de l’utilisateur dans [TeamsAppSetupPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps).
- Autoriser les utilisateurs dans un client pour interagir avec des applications personnalisées qui peuvent être gérées à un niveau client dans les paramètres d’application à l’échelle de l’organisation.
 
<sup>3</sup> applications par défaut et les applications externes peuvent être activées et désactivées au niveau de l’utilisateur dans TeamsAppPermissionPolicy. En outre, les applications peuvent être bloquées au niveau du client dans les paramètres d’application à l’échelle de l’organisation qui se substitue à tous les utilisateurs et les paramètres au niveau du client. 

> [!NOTE]
> Vous allez continuer à utiliser le tableau de bord de groupes dans le centre d’administration d’Office 365 pour configuration relatives aux équipes et canaux. Paramètres pour les applications restent dans la zone équipes du centre d’administration Office 365 et doit être migrés ultérieurement. 

## <a name="manage-settings-during-the-migration"></a>Gérer les paramètres lors de la migration

Vous pouvez continuer à modifier les paramètres dans le centre d’administration Office 365 et le Skype entreprise centre d’administration jusqu'à ce que la migration d’une section est terminée pour votre client. 

Le tableau suivant montre où vous pouvez gérer les fonctionnalités pendant la migration.

|Fonctionnalité  |Centre d’administration de Microsoft Teams                      |Skype pour Business admin center (hérité)  |Centre d’administration Office 365  |
|---------|:---------:|:---------:|:---------:|
|Stratégies de messagerie, les réunions et les événements Live des équipes     |     X    |         |         |
|Stratégie de mise à niveau d’équipes     |    X     |         |         |
|Paramètres invité pour la messagerie, les réunions et voix     |   X      |         |         |
|Gestion du cycle de vie des équipes   |    X    |      |       |
|Paramètres d’équipes   |    X    |      |       |
|Paramètres d’accès externe     |    X    |      |       |
|Gestion des utilisateurs    |         |         |    X     |    
|Audioconférence     |    X     |    X     |         |
|Forfaits d'appels     |         |    X     |         |
|Système téléphonique    |         |     X    |         |
|Gestion de numéros de téléphone     |         |   X      |         |
|Gestion des licences pour les fonctionnalités de voix dans le nuage     |         |         |    X     |
|Standards automatiques     |         |    X     |         |
|Files d'attente des appels     |         |    X     |         |

## <a name="manage-settings-after-the-migration"></a>Gérer les paramètres après la migration

Lors de la migration de ces paramètres est terminée, nous allons désactiver dans le centre d’administration Office 365 et le Skype pour le centre d’administration de Business, et ils peuvent être gérées dans le centre d’administration Microsoft Teams nouveau.


