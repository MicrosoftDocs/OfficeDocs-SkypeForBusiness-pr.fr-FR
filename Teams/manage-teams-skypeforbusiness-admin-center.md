---
title: Gérer les équipes pendant la transition vers le nouveau Microsoft Teams & Skype entreprise centre d’administration
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/05/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
description: Comprendre comment gérer les clients à l’échelle et les paramètres utilisateur pour les équipes pendant la transition entre les équipes expérience dans le centre d’administration Office 365 au nouveau Microsoft Teams & Skype entreprise centre d’administration.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
- Skype for Business Online
ms.openlocfilehash: 3dec789d31737eeb4585da5e28737a15ca679a5b
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26530574"
---
<a name="manage-teams-during-the-transition-to-the-new-microsoft-teams--skype-for-business-admin-center"></a>Gérer les équipes pendant la transition vers le nouveau Microsoft Teams & Skype entreprise centre d’administration
======================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

## <a name="what-is-the-new-microsoft-teams--skype-for-business-admin-center"></a>Quel est le nouveau Microsoft Teams & Skype entreprise centre d’administration ?  

La nouvelle expérience du centre d’administration vous fournira une expérience unifiée pour gérer des équipes et Skype pour les entreprises. Offrir des fonctionnalités supplémentaires, détails de bout en bout et la possibilité de gérer les paramètres des équipes sur un niveau de l’utilisateur.

![Capture d’écran des équipes Microsoft et Skype entreprise centre d’administration.](media/manage-teams-skype-for-business-admin-center-portal.png)

## <a name="settings-migrated-to-the-new-microsoft-teams--skype-for-business-admin-center"></a>Paramètres migrés vers le nouveau Microsoft Teams & Skype entreprise centre d’administration

Le tableau suivant identifie les sections de l’expérience des équipes qui ont été migrées et indique la relation entre les paramètres et les stratégies dans le nouveau portail d’administration.

|Section d’équipes dans le centre d’administration Office 365  |Nom du paramètre (niveau client)  |Microsoft Teams & Skype pour la stratégie d’entreprise centre d’administration   |Niveau : Client ou utilisateur   |
|---------|---------|---------|---------|
|Général     |Afficher la conversation d’organisation dans le profil personnel        |  [TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)       |  Client       |
|Général     |Utilisez Skype pour les entreprises pour les destinataires qui ne possèdent pas les équipes         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Client         |
|Général     |Autoriser les messages d’aide proactive T-Bot         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Client         |
|Intégration de la messagerie     |Autoriser les utilisateurs à envoyer des messages électroniques à canaux         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Client         |
|Intégration de la messagerie     |Autoriser les expéditeurs liste         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)        |Client         |
|Stockage cloud personnalisé     |Zone         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Client         |
|Stockage cloud personnalisé     |Échange        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Client         |
|Stockage cloud personnalisé     |Lecteur de Google        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Client         |
|Stockage cloud personnalisé     |ShareFile        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Client         |
|Paramètres par type de licence d’utilisateur     |Activer Microsoft Teams activé ou désactivé pour tous les utilisateurs          |Obsolètes<sup>1</sup>        |         |
|Équipes et canaux     |         |Redirige vers Azure Active Directory groupe Management (identique à l’expérience).              |Utilisateur         |
|Équipes et canaux     |         |Redirige vers la gestion de groupe DAS (identique à l’expérience).             |Utilisateur          |
|Les réunions et les appels     |Autoriser la planification de réunions privées         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Utilisateur          |
|Les réunions et les appels     |Autoriser les meetup du canal Ad hoc         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Utilisateur          |
|Les réunions et les appels     |Autoriser la planification de réunions de canal         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Utilisateur          |
|Les réunions et les appels     |Autoriser les vidéos de réunions         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Utilisateur          |
|Les réunions et les appels     |Autoriser les réunions de partage d’écran         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Utilisateur          |
|Les réunions et les appels     |Autorise les appels privée         |[TeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)        |Utilisateur          |
|Messagerie     |Activer Giphy afin que les utilisateurs peuvent ajouter des images GIF à des conversations         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Utilisateur         |
|Messagerie     |Évaluation du contenu         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Utilisateur         |
|Messagerie     |Activer les memes que les utilisateurs peuvent modifier et ajouter des conversations         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Utilisateur         |
|Messagerie     |Activer autocollants que les utilisateurs peuvent modifier et ajouter des conversations         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Utilisateur         |
|Messagerie     |Autoriser les propriétaires supprimer tous les messages         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Utilisateur         |
|Messagerie     |Permettre aux utilisateurs de modifier leurs propres messages         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Utilisateur         |
|Messagerie     |Autoriser les utilisateurs à supprimer leurs propres messages         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Utilisateur         |
|Messagerie     |Permet aux utilisateurs de chat privé         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Utilisateur         |

<sup>1</sup> déconseillée pour invité. Activation/désactivation de l’invité peut être géré maintenant dans le Microsoft Teams & Skype entreprise centre d’administration. Activation/désactivation des équipes pour l’entreprise, Edu étudiant, et Université Edu sera bientôt déconseillée. Il doit être gérée par l’attribution de licences dans le centre d’administration d’Office 365. Consultez la rubrique [gérer l’accès utilisateur aux équipes de Microsoft](user-access.md).

> [!NOTE]
> Vous allez continuer à utiliser le tableau de bord de groupes dans le centre d’administration d’Office 365 pour configuration relatives aux équipes et canaux. Paramètres pour les applications restent dans la zone équipes du centre d’administration Office 365 et doit être migrés ultérieurement. 

## <a name="manage-settings-during-the-migration"></a>Gérer les paramètres lors de la migration

Vous pouvez continuer à modifier les paramètres dans le centre d’administration Office 365 et le Skype entreprise centre d’administration jusqu'à ce que la migration d’une section est terminée pour votre client. 

Le tableau suivant montre où vous pouvez gérer les fonctionnalités pendant la migration.

|Fonctionnalité  |Les équipes Microsoft & Skype entreprise centre d’administration                       |Skype pour Business admin center (hérité)  |Centre d’administration Office 365  |
|---------|:---------:|:---------:|:---------:|
|Stratégies de messagerie, les réunions et les événements Live des équipes     |     X    |         |         |
|Stratégie de mise à niveau d’équipes     |    X     |         |         |
|Paramètres invité pour la messagerie, les réunions et voix     |   X      |         |         |
|Gestion du cycle de vie des équipes   |    X    |      |       |
|Paramètres d’équipes   |    X    |      |       |
|Paramètres d’accès externe     |    X    |      |       |
|Gestion des utilisateurs    |         |         |    X     |    
|Services d’audioconférence     |    X     |    X     |         |
|Forfaits d'appels     |         |    X     |         |
|Système téléphonique    |         |     X    |         |
|Gestion de numéros de téléphone     |         |   X      |         |
|Gestion des licences pour les fonctionnalités de voix dans le nuage     |         |         |    X     |
|Standards automatiques     |         |    X     |         |
|Files d'attente des appels     |         |    X     |         |

## <a name="manage-settings-after-the-migration"></a>Gérer les paramètres après la migration

Lors de la migration de ces paramètres est terminée, nous allons désactiver dans le centre d’administration Office 365 et le Skype pour le centre d’administration de Business, et ils peuvent être gérés dans le nouveau Microsoft Teams & Skype entreprise centre d’administration.


