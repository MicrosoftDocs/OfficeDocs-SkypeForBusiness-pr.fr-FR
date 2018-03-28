---
title: Gérer les équipes pendant la transition vers le nouveau Microsoft Teams et Skype pour Business Admin Center
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/23/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara
description: Comprendre la gestion des clients à l’échelle et les paramètres utilisateur pour les équipes pendant la transition entre les équipes d’expérience dans le centre d’administration d’Office 365 au nouveau Microsoft Teams & Skype pour Business Admin Center.
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
- Skype for Business Online
ms.openlocfilehash: 0f660130ce9fe2973178385e87433cac29fa8733
ms.sourcegitcommit: 39228142658557890b2173c41db9661eb502b946
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
<a name="manage-teams-during-the-transition-to-the-new-microsoft-teams-and-skype-for-business-admin-center"></a>Gérer les équipes pendant la transition vers le nouveau Microsoft Teams et Skype pour Business Admin Center
======================================================

Le nouveau centre d'administration Microsoft Teams et Skype Entreprise sera disponible prochainement ! 

À partir de mars 2018, nous sommes progressivement migration des paramètres à Skype pour le centre d’administration Business & Teams de Microsoft dans les deux le Skype en cours pour le centre d’administration de l’entreprise et rencontrer des Teams de Microsoft dans le centre d’administration d’Office 365. Si un paramètre a été migré, une notification s’affichera et vous serez dirigé vers son emplacement dans le nouveau centre d’administration Skype Entreprise.

Nous allons continuer à migrer des autres fonctionnalités de la Skype pour le centre d’administration de l’entreprise dans les mois à venir. Vous pouvez rester à jour via notre [plan d’évolution](https://aka.ms/Office365Roadmap)de public.

> [!NOTE]
> Nous déroulons le nouveau Microsoft Teams & Skype pour Business Admin Center en plusieurs étapes. Par conséquent, tous les clients verront pas le centre d’administration en même temps. Nous vous informerons lorsque vous pouvez démarrer le nouveau centre d’administration.

## <a name="what-is-the-new-microsoft-teams--skype-for-business-admin-center"></a>Quel est le nouveau Microsoft Teams & Skype pour Business Admin Center ?  

La nouvelle interface utilisateur Admin Center vous fournira une expérience unifiée pour gérer des équipes et Skype pour les entreprises. Nous offrons des fonctionnalités supplémentaires, les idées de bout en bout et la possibilité de gérer les paramètres des équipes sur un niveau de l’utilisateur.

![Capture d’écran des équipes de Microsoft et Skype pour entreprise Admin Center.](media/manage-teams-skype-for-business-admin-center-portal.png)


À compter de la mi-mars 2018, les fonctions suivantes seront disponibles dans le nouveau Microsoft Teams & Skype pour Business Admin Center : 

- **Stratégie de messagerie équipes Microsoft**: créer la stratégie pour la gestion au niveau de l’utilisateur de l’expérience du client Teams de Microsoft pour les scénarios de messagerie.
- **Stratégie d’interopérabilité équipes Microsoft**: configuration de l’expérience de l’interopérabilité entre Skype pour les entreprises et les Teams de Microsoft.
- **Invité les équipes Microsoft messaging paramètres**: contrôler les fonctionnalités de messagerie pour les comptes invité dans Teams de Microsoft. 
- **Paramètres de fédération**: gérer la fédération entre les locataires pour Microsoft Teams et Skype pour les entreprises. 
- **Gestion des utilisateurs**: affecter des stratégies et de configurer des comptes d’utilisateurs. 
- **Audioconférence**: configurer des numéros d’accès à distance et les paramètres pour Skype pour les entreprises et les Teams de Microsoft. 

 

## <a name="settings-migrated-to-the-new-microsoft-teams--skype-for-business-admin-center"></a>Paramètres migrés vers le nouveau Microsoft Teams & Skype pour Business Admin Center

Vos paramètres existants pour général, E-mail intégration, personnalisé stockage en nuage, les appels et réunions et messagerie dans Teams de Microsoft (voir image ci-dessous) seront migrés vers le nouveau Microsoft Teams & Skype pour le centre d’administration commerciale (également connu sous le nom du nouveau portail Admin) dans les prochains mois. 



> [!NOTE]
>Vous allez continuer à utiliser le tableau de bord de groupes dans le centre d’administration d’Office 365 pour la configuration relative à des **équipes et des canaux**. Paramètres pour les **applications** demeurent dans la zone équipes du centre d’administration d’Office 365 et seront migrés ultérieurement. 

![Page de capture d’écran des équipes dans le centre d’administration d’Office 365.](media/manage-teams-skypeforbusiness-admin-center-teams-in-O365.png)

En ce qui concerne les paramètres disponibles dans **paramètres par type de licence d’utilisateur**, il fourni essentiellement un moyen de configurer différemment les groupes d’utilisateurs. Désormais, avec le nouveau portail d’administration, vous pouvez le faire sur une base par utilisateur. 


Le type de licence sera migré. Si vous utilisez actuellement le **Équipes Microsoft activer ou désactiver pour tous les utilisateurs de ce type** de paramètre pour contrôler l’accès aux équipes pour les utilisateurs sur les points de stock, nous maintiendrons votre configuration actuelle. Toutefois, vous ne pourrez pas modifier ce paramètre dans le portail d’administration. Au lieu de cela, vous allez attribuer les licences appropriées aux utilisateurs dans vos clients via le centre d’administration Office 365. Pour plus d’informations, consultez [gérer l’accès des utilisateurs à des équipes de Microsoft](user-access.md). 

Le tableau suivant identifie les sections de l’expérience d’équipes en cours qui seront migrés et illustre la relation entre les stratégies et les paramètres actuels dans le nouveau portail d’administration.


|Section des équipes dans le centre d’administration d’Office 365  |Nom du paramètre (niveau de clients)  |Microsoft Teams & Skype pour la stratégie d’entreprise Admin Center   |Niveau : Locataire ou utilisateur   |
|---------|---------|---------|---------|
|Général     |Afficher la conversation d’organisation dans le profil personnel        |  TeamsClientConfiguration       |  Clients       |
|Général     |Utiliser Skype pour les entreprises de destinataires n’ayant pas d’équipes         |TeamsClientConfiguration         |Clients         |
|Général     |Autoriser les messages d’aide proactive T-Bot         |TeamsClientConfiguration         |Clients         |
|Intégration de la messagerie     |Autoriser les utilisateurs à envoyer des e-mails aux canaux         |TeamsClientConfiguration         |Clients         |
|Intégration de la messagerie     |Autoriser les expéditeurs liste         |TeamsClientConfiguration        |Clients         |
|Stockage cloud personnalisé     |Zone         |TeamsClientConfiguration         |Clients         |
|Stockage cloud personnalisé     |Boîte de dépôt        |TeamsClientConfiguration         |Clients         |
|Stockage cloud personnalisé     |Lecteur de Google        |TeamsClientConfiguration         |Clients         |
|Stockage cloud personnalisé     |ShareFile        |TeamsClientConfiguration         |Clients         |
|Paramètres par type de licence d’utilisateur     |Activer ou désactiver les Teams de Microsoft pour tous les utilisateurs          |Déconseillée. Office 365 admin center permet d’attribuer des licences.        |         |
|Équipes et canaux     |         |Effectue une redirection vers Azure groupe gestion de Active Directory (identique à l’expérience actuelle).              |Utilisateur         |
|Équipes et canaux     |         |Effectue une redirection vers la gestion de groupe DAS (identique à l’expérience actuelle).             |Utilisateur          |
|Les réunions et les appels     |Autoriser la planification de réunions privées         |TeamsMeetingPolicy         |Utilisateur          |
|Les réunions et les appels     |Autoriser la meetup de canal Ad hoc         |TeamsMeetingPolicy         |Utilisateur          |
|Les réunions et les appels     |Autoriser la planification de réunions de canal         |TeamsMeetingPolicy         |Utilisateur          |
|Les réunions et les appels     |Autoriser les vidéos de réunions         |TeamsMeetingPolicy         |Utilisateur          |
|Les réunions et les appels     |Permettre aux réunions de partage d’écran         |TeamsMeetingPolicy         |Utilisateur          |
|Les réunions et les appels     |Autorise les appels privés         |TeamsCallingPolicy         |Utilisateur          |
|Messagerie     |Activer Giphy afin que les utilisateurs peuvent ajouter des fichiers GIF lors de conversations         |TeamsMessagingPolicy         |Utilisateur         |
|Messagerie     |Évaluation du contenu         |TeamsMessagingPolicy         |Utilisateur         |
|Messagerie     |Activer les memes que les utilisateurs peuvent modifier et de conversations         |TeamsMessagingPolicy         |Utilisateur         |
|Messagerie     |Activer les autocollants que les utilisateurs peuvent modifier et de conversations         |TeamsMessagingPolicy         |Utilisateur         |
|Messagerie     |Autoriser les propriétaires supprimer tous les messages         |TeamsMessagingPolicy         |Utilisateur         |
|Messagerie     |Autoriser les utilisateurs à modifier leurs propres messages.         |TeamsMessagingPolicy         |Utilisateur         |
|Messagerie     |Autoriser les utilisateurs à supprimer leurs propres messages.         |TeamsMessagingPolicy         |Utilisateur         |
|Messagerie     |Permet aux utilisateurs de converser en privé         |TeamsMessagingPolicy         |Utilisateur         |



## <a name="manage-settings-during-the-migration"></a>Gérer les paramètres lors de la migration

Nous avons l’intention de migrer des paramètres d’équipes dans les sections dans l’ordre suivant : la messagerie, les réunions, les appels et enfin, les sections de la stratégie de Configuration de TeamsClient (général, intégration de la messagerie et de stockage en nuage personnalisé).   

Vous pouvez continuer à modifier les paramètres dans le centre d’administration d’Office 365 et le Skype pour le centre d’administration d’entreprise jusqu'à ce que la migration d’une section est complète pour vos clients. 

Le tableau suivant montre où vous pouvez gérer les fonctionnalités lors de la migration.

|Fonctionnalité  |Les équipes Microsoft et Skype pour entreprise Admin Center                       |Skype pour entreprise Admin Center (hérité)  |Centre d’administration Office 365  |
|---------|:---------:|:---------:|:---------:|
|Stratégie de messagerie     |     X    |         |         |
|Stratégie d’interopérabilité équipes     |    X     |         |         |
|Paramètres de messagerie d’invité     |   X      |         |         |
|Paramètres d’accès externe    |    X     |         |         |
|Gestion des utilisateurs    |         |         |    X     |    
|Conférence audio     |    X     |    X     |         |
|Forfaits d'appels     |         |    X     |         |
|Système téléphonique    |         |     X    |         |
|Gestion de numéros de téléphone     |         |   X      |         |
|Licences pour les fonctionnalités vocales de nuage     |         |         |    X     |
|Standards automatiques     |         |    X     |         |
|Files d'attente des appels     |         |    X     |         |

## <a name="manage-settings-after-the-migration"></a>Gérer les paramètres après la migration

Vous serez averti une fois la migration terminée pour une section spécifique au sein des équipes. À ce moment-là, vous serez en mesure de voir vos paramètres existants pour cette section dans le centre d’administration d’Office 365, mais vous ne pourrez pas apporter des modifications il. Au lieu de cela, vous utiliserez le Microsoft Teams & Skype pour Business Admin Center pour gérer les paramètres nouvellement migrés.

Lors de la migration de ces paramètres est terminée, nous allons les désactiver dans le centre d’administration d’Office 365 et le Skype pour le centre d’administration de l’entreprise.


