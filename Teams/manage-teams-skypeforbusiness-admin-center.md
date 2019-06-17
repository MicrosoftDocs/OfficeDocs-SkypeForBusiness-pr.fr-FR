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
description: Apprenez à gérer les paramètres utilisateur et à l’échelle du client pour les équipes lors de la transition de l’utilisation de teams dans le centre d’administration Microsoft 365 vers le nouveau centre d’administration Microsoft Teams.
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
ms.openlocfilehash: 92af57f0704ae00164db143d3948b5baf59f6105
ms.sourcegitcommit: f735495849f02e0ea23c7d6f250e9c0656daeea1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/13/2019
ms.locfileid: "34933779"
---
<a name="manage-teams-during-the-transition-to-the-new-microsoft-teams-admin-center"></a>Gérer Teams lors de la transition vers le nouveau Centre d’administration de Microsoft Teams
======================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

## <a name="what-is-the-new-microsoft-teams-admin-center"></a>Qu’est-ce que le nouveau centre d’administration de Microsoft teams?  

Le nouveau centre d’administration offrira une interface unifiée pour gérer les équipes et Skype entreprise. Nous proposons des fonctionnalités supplémentaires, des analyses de bout en bout et la possibilité de gérer les paramètres d’équipe sur un niveau utilisateur.

![Capture d’écran du centre d’administration Microsoft Teams.](media/manage-teams-skype-for-business-admin-center-portal.png)

## <a name="settings-migrated-to-the-new-microsoft-teams-admin-center"></a>Paramètres migrés vers le nouveau centre d’administration Microsoft teams

Le tableau suivant identifie les sections de l’interface d’équipe qui ont été migrées et indique la relation entre les paramètres actuels et les stratégies du nouveau portail d’administration.

|Section d’équipes dans le centre d’administration 365 Microsoft  |Nom du paramètre (niveau du client)  |Stratégie du centre d’administration Microsoft teams   |Niveau: client ou utilisateur   |
|---------|---------|---------|---------|
|Général     |Afficher la discussion d’organisation dans le profil personnel        |  [TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)       |  Améliorations       |
|Général     |Utiliser Skype entreprise pour les destinataires qui ne disposent pas de Microsoft teams         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Améliorations         |
|Intégration de courrier électronique     |Autoriser les utilisateurs à envoyer des messages électroniques à des canaux         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Améliorations         |
|Intégration de courrier électronique     |Liste des expéditeurs autorisés         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)        |Améliorations         |
|Stockage cloud personnalisé     |Boite         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Améliorations         |
|Stockage cloud personnalisé     |Échange        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Améliorations         |
|Stockage cloud personnalisé     |Google Drive        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Améliorations         |
|Stockage cloud personnalisé     |ShareFile        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Améliorations         |
|Paramètres par utilisateur/type de licence     |Activation ou désactivation de Microsoft teams pour tous les utilisateurs          |Déconseillé<sup>1</sup>        |         |
|Équipes et canaux     |         |Redirectionne la gestion des groupes Azure Active Directory (comme l’interface actuelle).              |Utilisateur         |
|Équipes et canaux     |         |Redirectionne vers la gestion des groupes AAD (similaire à l’interface actuelle).             |Utilisateur          |
|Applications|Activer les applications externes nouvelles par défaut|Paramètres d’application à l’échelle de l’Organisation|Améliorations|
|Applications|Autoriser les applications externes|Paramètres d’application à l’échelle de l’Organisation|Améliorations|
|Applications|Autoriser le chargement indépendant d’applications externes du<sup>2</sup>|[TeamsAppSetupPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps)|Utilisateur|
|Applications|Applications par défaut<sup>3</sup>|TeamsAppPermissionPolicy|Utilisateur|
|Applications|Applications externes<sup>3</sup>|TeamsAppPermissionPolicy|Utilisateur|
|Appels et réunions     |Autoriser la planification de réunions privées         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Utilisateur          |
|Appels et réunions     |Autoriser le Meetup de canal ad hoc         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Utilisateur          |
|Appels et réunions     |Autoriser la planification de réunions de canal         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Utilisateur          |
|Appels et réunions     |Autoriser les vidéos dans les réunions         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Utilisateur          |
|Appels et réunions     |Autoriser le partage d’écran dans les réunions         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Utilisateur          |
|Appels et réunions     |Autoriser les appels privés         |[TeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)        |Utilisateur          |
|Messagerie      |Activer Giphy pour permettre aux utilisateurs d’ajouter des fichiers GIF à des conversations         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Utilisateur         |
|Messagerie      |Évaluation du contenu         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Utilisateur         |
|Messagerie      |Activez mèmes que les utilisateurs peuvent modifier et ajouter aux conversations         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Utilisateur         |
|Messagerie      |Activer les autocollants que les utilisateurs peuvent modifier et ajouter aux conversations         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Utilisateur         |
|Messagerie      |Autoriser les propriétaires à supprimer tous les messages         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Utilisateur         |
|Messagerie      |Permettre aux utilisateurs de modifier leurs propres messages         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Utilisateur         |
|Messagerie      |Autoriser les utilisateurs à supprimer leurs propres messages         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Utilisateur         |
|Messagerie      |Permet aux utilisateurs de discuter en privé         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Utilisateur         |

<sup>1</sup> déconseillé pour les invités. L’activation/désactivation de invités peut désormais être gérée dans le centre d’administration Microsoft Teams. L’activation/désactivation de teams pour les entreprises, des étudiants edu et des universités edu sera bientôt désapprouvée. Pour ce faire, vous devez affecter des licences dans le centre d’administration Microsoft 365. Voir [gérer l’accès des utilisateurs à Microsoft teams](user-access.md).
<br><br>
<sup>2</sup> chargement indépendant est scindé comme suit:

- Autorisez un utilisateur à charger des applications qui peuvent être gérées à un utilisateur dans [TeamsAppSetupPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps).
- Autorisez les utilisateurs d’un client à interagir avec des applications personnalisées qui peuvent être gérées au niveau du client dans les paramètres d’application à l’échelle de l’organisation.
 
<sup>3</sup> les applications et applications externes par défaut peuvent être activées et désactivées au niveau de l’utilisateur dans TeamsAppPermissionPolicy. De plus, les applications peuvent être bloquées au niveau du client dans les paramètres de l’application à l’échelle de l’organisation qui remplace les paramètres utilisateur et de niveau client. 

> [!NOTE]
> Vous pouvez toujours utiliser le tableau de bord groupes dans le centre d’administration Microsoft 365 pour la configuration liée aux équipes et aux canaux. Les paramètres des applications resteront dans la zone équipes du centre d’administration Microsoft 365 et seront migrés plus tard. 

## <a name="manage-settings-during-the-migration"></a>Gérer les paramètres lors de la migration

Vous pouvez continuer à modifier les paramètres dans le centre d’administration Microsoft 365 et le centre d’administration Skype entreprise jusqu’à ce que la migration pour une section soit terminée pour votre client. 

Le tableau suivant indique les emplacements où vous pouvez gérer les fonctionnalités lors de la migration.

|Fonctionnalité  |Centre d’administration Microsoft teams                      |Centre d’administration Skype entreprise (hérité)  |Centre d’administration Microsoft 365  |
|---------|:---------:|:---------:|:---------:|
|Stratégies de messagerie, de réunions et d’événements en direct teams     |     X    |         |         |
|Stratégie de mise à niveau des équipes     |    X     |         |         |
|Paramètres d’invité pour la messagerie, les réunions et la voix     |   X      |         |         |
|Gestion du cycle de vie des équipes   |    X    |      |       |
|Paramètres des équipes   |    X    |      |       |
|Paramètres d’accès externe     |    X    |      |       |
|Gestion des utilisateurs    |         |         |    X     |    
|Audioconférence     |    X     |    X     |         |
|Forfaits d'appels     |         |    X     |         |
|Système téléphonique    |         |     X    |         |
|Gestion des numéros de téléphone     |         |   X      |         |
|Licences pour les fonctionnalités vocales sur le Cloud     |         |         |    X     |
|Standards automatiques     |         |    X     |         |
|Files d'attente des appels     |         |    X     |         |

## <a name="manage-settings-after-the-migration"></a>Gérer les paramètres après la migration

Lorsque la migration de ces paramètres est terminée, nous les désactivons dans le centre d’administration Office 365 et le centre d’administration Skype entreprise, et ils peuvent être gérés dans le nouveau centre d’administration Microsoft Teams.


## <a name="edu-migration-june-july-2019"></a>Migration EDU juin-2019

En juin et 2019, les clients EDU restants seront migrés de l’ancienne version d’administration (dans le centre d’administration Microsoft 365) vers le centre d’administration Teams. Consultez le centre de messages (dans le centre d’administration 365 Microsoft) pour en savoir plus sur la migration. Voici ce qui apparaît une fois que vous avez effectué la migration:

|Section d’équipes dans le centre d’administration 365 Microsoft  |Nom du paramètre (niveau du client)  |Stratégie du centre d’administration Microsoft teams   |Niveau: client ou utilisateur   |
|---------|---------|---------|---------|  
| Messagerie   |Les propriétaires peuvent supprimer des messages envoyés |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | Utilisateur |
| Messagerie  | Les utilisateurs peuvent supprimer des messages envoyés |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | Utilisateur |
| Messagerie   | Les utilisateurs peuvent modifier les messages envoyés |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)  |Utilisateur|
| Messagerie  | Permettre aux utilisateurs de discuter |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | Utilisateur |
| Messagerie  | Utiliser Giphys dans les conversations | [TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | Utilisateur |
| Messagerie  | Évaluation du contenu Giphy | [TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | Utilisateur |
| Messagerie  | Utiliser mèmes dans les conversations  |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | Utilisateur |
| Messagerie  | Utiliser les autocollants dans les conversations |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | Utilisateur |

De plus, Voici les paramètres qui sont uniquement disponibles dans le centre d’administration Microsoft teams:

|Nom du paramètre | Stratégie du centre d’administration Microsoft teams | Niveau: client ou utilisateur
|-------------|-------------------------------------|---------|
|Autoriser les aperçus d’URL | [TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | Utilisateur |
|Autoriser un utilisateur à supprimer des utilisateurs d’une conversation de groupe |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | Utilisateur |
|Autoriser le lecteur immersif à afficher les messages |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)| Utilisateur |
|Permettre aux utilisateurs de traduire des messages |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)| Utilisateur |
|Confirmations de lecture | [TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | Utilisateur |
|Les utilisateurs peuvent envoyer des notifications de priorité | [TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | Utilisateur |
|Creation de messages vocaux |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmessagingpolicy?view=skype-ps)| Utilisateur |
|Sur les appareils mobiles, afficher les canaux préférés au-dessus des discussions récentes |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmessagingpolicy?view=skype-ps)| Utilisateur |
