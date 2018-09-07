---
title: Gérer les équipes pendant la transition vers le nouveau Microsoft Teams et Skype entreprise centre d’administration
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/23/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
description: Comprendre comment gérer les clients à l’échelle et les paramètres utilisateur pour les équipes pendant la transition entre les équipes expérience dans le centre d’administration d’Office 365 pour le nouveau Microsoft Teams & Skype entreprise centre d’administration.
localization_priority: Priority
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
- Skype for Business Online
ms.openlocfilehash: b81853b33f457dd8a69890774b4b7ff8902d8226
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23864826"
---
<a name="manage-teams-during-the-transition-to-the-new-microsoft-teams-and-skype-for-business-admin-center"></a>Gérer les équipes pendant la transition vers le nouveau Microsoft Teams et Skype entreprise centre d’administration
======================================================

Le nouveau centre d'administration Microsoft Teams et Skype Entreprise sera disponible prochainement ! 

À compter de 2018 mars, nous allons progressivement migration des paramètres Microsoft Teams & Skype entreprise centre d’administration à partir de deux le Skype actuel pour le centre d’administration Business et une expérience le Teams Microsoft dans le centre d’administration d’Office 365. Si un paramètre a été migré, une notification s’affichera et vous serez dirigé vers son emplacement dans le nouveau centre d’administration Skype Entreprise.

Nous allons continuer à migrer d’autres fonctionnalités de la Skype pour le centre d’administration Business dans les mois à venir. Vous pouvez rester à jour par le biais de notre public de la [feuille de route](https://aka.ms/Office365Roadmap).

> [!NOTE]
> Nous allons présentant la nouvelle Teams Microsoft & Skype pour le centre d’administration Business par étapes. Par conséquent, tous les clients verront pas le nouveau centre d’administration en même temps. Nous allons vous informer lorsque vous pouvez commencer à utiliser le nouveau centre d’administration.

## <a name="what-is-the-new-microsoft-teams--skype-for-business-admin-center"></a>Quel est le nouveau Microsoft Teams & Skype entreprise centre d’administration ?  

La nouvelle expérience du centre d’administration vous fournira une expérience unifiée pour gérer des équipes et Skype pour les entreprises. Offrir des fonctionnalités supplémentaires, détails de bout en bout et la possibilité de gérer les paramètres des équipes sur un niveau de l’utilisateur.

![Capture d’écran des équipes Microsoft et Skype entreprise centre d’administration.](media/manage-teams-skype-for-business-admin-center-portal.png)


À compter de la mi-mars 2018, les fonctionnalités suivantes étaient disponibles dans le nouveau Microsoft Teams & Skype entreprise centre d’administration : 

- **Stratégie de messagerie équipes Microsoft**: créer la stratégie de gestion de niveau utilisateur de l’expérience du client Microsoft Teams pour les scénarios de messagerie.
- **Stratégie de mise à niveau des équipes Microsoft**: configuration de l’expérience de l’interopérabilité et mise à niveau entre Skype pour les entreprises et Teams Microsoft. Voir, https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype. 
- **Les équipes Microsoft invité paramètres de messagerie**: contrôler les fonctionnalités de messagerie pour les comptes invité dans Microsoft Teams. 
- **Paramètres de fédération**: gérer la fédération entre clients pour Microsoft Teams et Skype pour les entreprises. 
- **Gestion des utilisateurs**: attribuer des stratégies et configurer des comptes d’utilisateurs. 
- **Audioconférence**: configurer les paramètres pour Skype pour les entreprises et Teams Microsoft et les numéros de téléphone. 

 

## <a name="settings-migrated-to-the-new-microsoft-teams--skype-for-business-admin-center"></a>Paramètres migrés vers le nouveau Microsoft Teams & Skype entreprise centre d’administration

Vos paramètres existants pour général, messagerie intégration, personnalisé stockage en nuage, appels et des réunions et la messagerie dans Microsoft Teams (voir l’image ci-dessous) seront migrées vers le nouveau Microsoft Teams & Skype pour Business Admin Center (également connu sous le nouveau portail d’administration) dans les prochains mois. 



> [!NOTE]
>Vous allez continuer à utiliser le tableau de bord de groupes dans le centre d’administration d’Office 365 pour configuration relatives aux **équipes et canaux**. Paramètres pour les **applications** restent dans la zone équipes du centre d’administration d’Office 365 et doit être migrés ultérieurement. 

![Page de la capture d’écran des équipes dans le centre d’administration d’Office 365.](media/manage-teams-skypeforbusiness-admin-center-teams-in-O365.png)

En ce qui concerne les paramètres disponibles dans les **paramètres par type de licence d’utilisateur**, il fourni essentiellement un moyen de configurer des groupes d’utilisateurs différemment. À présent, avec le nouveau portail d’administration, vous pouvez le faire dans par utilisateur. 


Le type de licence doit être migré. Si vous utilisez actuellement le paramètre **Équipes Microsoft activer ou désactiver pour tous les utilisateurs de ce type** pour contrôler l’accès aux équipes pour les utilisateurs entre les versions clientes, nous conserve vos configurations actuelles. Toutefois, vous ne pourrez pas modifier ce paramètre dans le nouveau portail d’administration. Au lieu de cela, vous allez attribuer les licences appropriés aux utilisateurs dans votre client via le centre d’administration Office 365. Pour plus d’informations, voir [gérer l’accès utilisateur aux équipes de Microsoft](user-access.md). 

Le tableau suivant identifie les sections de l’expérience d’équipes en cours qui seront migrés et indique la relation entre les paramètres et les stratégies dans le nouveau portail d’administration.


|Section d’équipes dans le centre d’administration d’Office 365  |Nom du paramètre (niveau client)  |Microsoft Teams & Skype pour la stratégie d’entreprise centre d’administration   |Niveau : Client ou utilisateur   |
|---------|---------|---------|---------|
|Général     |Afficher la conversation d’organisation dans le profil personnel        |  TeamsClientConfiguration       |  Client       |
|Général     |Utilisez Skype pour les entreprises pour les destinataires qui ne possèdent pas les équipes         |TeamsClientConfiguration         |Client         |
|Général     |Autoriser les messages d’aide proactive T-Bot         |TeamsClientConfiguration         |Client         |
|Intégration de la messagerie     |Autoriser les utilisateurs à envoyer des messages électroniques à canaux         |TeamsClientConfiguration         |Client         |
|Intégration de la messagerie     |Autoriser les expéditeurs liste         |TeamsClientConfiguration        |Client         |
|Stockage cloud personnalisé     |Zone         |TeamsClientConfiguration         |Client         |
|Stockage cloud personnalisé     |Échange        |TeamsClientConfiguration         |Client         |
|Stockage cloud personnalisé     |Lecteur de Google        |TeamsClientConfiguration         |Client         |
|Stockage cloud personnalisé     |ShareFile        |TeamsClientConfiguration         |Client         |
|Paramètres par type de licence d’utilisateur     |Activer Microsoft Teams activé ou désactivé pour tous les utilisateurs          |Obsolète. Utilisez le centre d’administration Office 365 à l’attribution de licences.        |         |
|Équipes et canaux     |         |Redirige vers Azure Active Directory groupe Management (identique à l’expérience).              |Utilisateur         |
|Équipes et canaux     |         |Redirige vers la gestion de groupe DAS (identique à l’expérience).             |Utilisateur          |
|Les réunions et les appels     |Autoriser la planification de réunions privées         |TeamsMeetingPolicy         |Utilisateur          |
|Les réunions et les appels     |Autoriser les meetup du canal Ad hoc         |TeamsMeetingPolicy         |Utilisateur          |
|Les réunions et les appels     |Autoriser la planification de réunions de canal         |TeamsMeetingPolicy         |Utilisateur          |
|Les réunions et les appels     |Autoriser les vidéos de réunions         |TeamsMeetingPolicy         |Utilisateur          |
|Les réunions et les appels     |Autoriser les réunions de partage d’écran         |TeamsMeetingPolicy         |Utilisateur          |
|Les réunions et les appels     |Autorise les appels privée         |TeamsCallingPolicy         |Utilisateur          |
|Messagerie     |Activer Giphy afin que les utilisateurs peuvent ajouter des images GIF à des conversations         |TeamsMessagingPolicy         |Utilisateur         |
|Messagerie     |Évaluation du contenu         |TeamsMessagingPolicy         |Utilisateur         |
|Messagerie     |Activer les memes que les utilisateurs peuvent modifier et ajouter des conversations         |TeamsMessagingPolicy         |Utilisateur         |
|Messagerie     |Activer autocollants que les utilisateurs peuvent modifier et ajouter des conversations         |TeamsMessagingPolicy         |Utilisateur         |
|Messagerie     |Autoriser les propriétaires supprimer tous les messages         |TeamsMessagingPolicy         |Utilisateur         |
|Messagerie     |Permettre aux utilisateurs de modifier leurs propres messages         |TeamsMessagingPolicy         |Utilisateur         |
|Messagerie     |Autoriser les utilisateurs à supprimer leurs propres messages         |TeamsMessagingPolicy         |Utilisateur         |
|Messagerie     |Permet aux utilisateurs de chat privé         |TeamsMessagingPolicy         |Utilisateur         |



## <a name="manage-settings-during-the-migration"></a>Gérer les paramètres lors de la migration

Nous prévoyons de migrer les paramètres d’équipes dans les sections dans l’ordre suivant : messagerie, réunions, les appels et enfin, les sections de la stratégie de Configuration TeamsClient (général, l’intégration de messagerie et de stockage en nuage personnalisé).   

Vous pouvez continuer à modifier les paramètres dans le centre d’administration d’Office 365 et le Skype pour le centre d’administration Business jusqu'à ce que la migration d’une section est terminée pour votre client. 

Le tableau suivant montre où vous pouvez gérer les fonctionnalités pendant la migration.

|Fonctionnalité  |Les équipes Microsoft et Skype entreprise centre d’administration                       |Skype pour Business Admin Center (hérité)  |Centre d’administration Office 365  |
|---------|:---------:|:---------:|:---------:|
|Stratégie de messagerie     |     X    |         |         |
|Stratégie d’interopérabilité de base équipes     |    X     |         |         |
|Paramètres de messagerie invité     |   X      |         |         |
|Paramètres d’accès externe    |    X     |         |         |
|Gestion des utilisateurs    |         |         |    X     |    
|Services d’audioconférence     |    X     |    X     |         |
|Forfaits d'appels     |         |    X     |         |
|Système téléphonique    |         |     X    |         |
|Gestion de numéros de téléphone     |         |   X      |         |
|Gestion des licences pour les fonctionnalités de voix dans le nuage     |         |         |    X     |
|Standards automatiques     |         |    X     |         |
|Files d'attente des appels     |         |    X     |         |

## <a name="manage-settings-after-the-migration"></a>Gérer les paramètres après la migration

Nous allons vous informer après que la migration est terminée pour une section spécifique au sein des équipes. À ce stade, vous serez en mesure de voir vos paramètres existants de cette section dans le centre d’administration d’Office 365, mais vous ne pourrez pas apporter des modifications il. Au lieu de cela, vous allez utiliser le Microsoft Teams & Skype entreprise centre d’administration pour gérer les paramètres récemment migrées.

Lors de la migration de ces paramètres est terminée, nous allons les désactiver dans le centre d’administration d’Office 365 et le Skype pour le centre d’administration Business.


