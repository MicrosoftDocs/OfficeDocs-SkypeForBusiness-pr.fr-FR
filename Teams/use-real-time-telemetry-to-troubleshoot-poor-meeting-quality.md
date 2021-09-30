---
title: Utiliser la télémétrie en temps réel pour résoudre les problèmes de qualité des réunions
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, vkorlep
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
- Reporting
description: Utilisez la télémétrie en temps réel avec des détails sur les appareils, les réseaux et la connectivité pour résoudre les problèmes des utilisateurs Microsoft Teams réunions programmées.
ms.openlocfilehash: c33e3309995d82fd16e9eb1deb2fa5fe24b04330
ms.sourcegitcommit: 5eb5acd7910724f7f4a598ecc28b003e5bbe5ea5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "60007906"
---
# <a name="use-real-time-telemetry-to-troubleshoot-poor-meeting-quality"></a>Utiliser la télémétrie en temps réel pour résoudre les problèmes de qualité des réunions

> [!NOTE]
> Cette fonctionnalité est actuellement en prévisualisation publique.

Cet article explique comment utiliser la télémétrie en temps réel pour résoudre des problèmes de qualité Microsoft Teams réunion pour des utilisateurs individuels. Vous pouvez consulter la télémétrie en temps réel si vous avez l’un des rôles suivants :

- Administrateur Teams
- Teams Spécialiste du support pour les communications
- Ingénieur du support technique pour les communications Teams

Pour plus d’informations sur Teams rôles d’administrateur, voir Utiliser Microsoft Teams rôles d’administrateur [pour gérer Teams.](/MicrosoftTeams/using-admin-roles)

La télémétrie en temps réel permet aux administrateurs informatiques d’examiner les réunions programmées de leurs utilisateurs importants et de voir les problèmes audio, vidéo, de partage de contenu et de réseau. En tant qu’administrateur, vous pouvez utiliser la télémétrie pour examiner ces problèmes pendant les réunions et résoudre les problèmes en temps réel.

## <a name="what-is-real-time-telemetry"></a>Qu’est-ce que la télémétrie en temps réel ?

Aujourd’hui, la résolution des problèmes de réunion individuelle est disponible pour les administrateurs Teams par le biais de l’analyse des appels [à](use-call-analytics-to-troubleshoot-poor-call-quality.md) l’issue de la réunion. La télémétrie en temps réel permet aux administrateurs de résoudre les problèmes des réunions programmées lorsqu’ils sont en cours.

La télémétrie en temps réel affiche des informations détaillées sur les Teams utilisateurs de votre compte Office 365 mis à jour en temps réel. Il inclut des informations sur les périphériques, le réseau, la connectivité, l’audio, la vidéo et les problèmes de partage de contenu, qui aideront les administrateurs à résoudre les problèmes de qualité des appels de façon plus efficace.

En tant qu Teams de projet, vous avez un accès total à toutes les données de télémétrie en temps réel pour chaque utilisateur. De plus, vous pouvez attribuer des rôles Azure Active Directory au personnel de support technique. Pour en savoir plus sur ces rôles, voir [Accorder l’autorisation au support technique et au personnel de support technique.](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff)

## <a name="where-to-find-per-user-real-time-troubleshooting-telemetry"></a>Où trouver la résolution des problèmes de télémétrie en temps réel par utilisateur

Pour voir toutes les informations et données de réunion d’un utilisateur, rendez-vous dans le [Teams d’administration.](https://admin.teams.microsoft.com) Sous **Gérer les**  >  **utilisateurs,** sélectionnez un utilisateur, puis ouvrez l’onglet & **d’appels** sur la page de profil de l’utilisateur. Sous Réunions **récentes,** vous verrez la liste des réunions que l’utilisateur a participé au cours des 24 dernières heures pour lesquelles la télémétrie en temps réel est *disponible,* y compris les réunions en cours. Si la réunion n’est pas en cours ou ne comprend pas de données de télémétrie en temps réel, elle s’affiche dans **réunions passées.**

![Capture d’écran de la table réunions récentes.](media/recent-meetings.png)

Pour obtenir des informations supplémentaires sur les participants d’une réunion en cours, notamment les statistiques sur l’appareil, le réseau et l’audio, recherchez la réunion dans Réunions **récentes** et sélectionnez le lien sous la colonne **Participants.**

![Capture d’écran du tableau des détails des participants.](media/participant-details.png)

Pour examiner la télémétrie en temps réel d’un utilisateur donné pour une réunion en cours, notamment des informations sur l’appareil, le réseau, l’audio, la vidéo et les détails du partage de contenu, sélectionnez **l’ID** de réunion.

![Capture d’écran des données de session des utilisateurs d’analyse des appels.](media/real-time-telemetry.png)

## <a name="platforms-supported-for-real-time-telemetry"></a>Plateformes prise en charge pour la télémétrie en temps réel

- Windows
- macOS
- Linux
- Android
- iOS

## <a name="teams-devices-support-with-real-time-telemetry"></a>Teams prise en charge des appareils avec la télémétrie en temps réel

- MTR - Surface Hub
- MTR - affichage Teams’écran
- MTR - Barre de collaboration
- Appareils IP Téléphone ip

## <a name="limitations"></a>Limites

- La télémétrie en temps réel est disponible uniquement pour les réunions prévues. Pour les réunions ad hoc telles que Conférence maintenant, PSTN, appels 1:1 et appels de groupe, la télémétrie en temps réel ne fonctionne pas.
- La télémétrie en temps réel n’est disponible que pour les présentateurs d’un événement en direct programmé. Il n’est actuellement pas disponible pour les participants à un événement en direct.
- Les données de télémétrie en temps réel sont disponibles pour une réunion sous Réunions **récentes** 24 heures après la fin de la réunion. Au bout de 24 heures, vous ne pouvez plus accéder aux données et la réunion passe aux **réunions passées.** Si une réunion dure plus de 3 heures, la télémétrie en temps réel ne sera disponible que pour les *3 dernières heures.*
- La télémétrie ne fonctionne pas avec les versions antérieures d’Teams. Si aucune télémétrie n’est disponible, essayez de mettre à jour votre client.
- Si des participants externes ou des utilisateurs  anonymes rejoignent une réunion, leur nom d’affichage s’affiche comme indisponible pour conserver la confidentialité entre clients.

## <a name="related-topics"></a>Voir aussi

[Configurer l’analyse des appels par utilisateur](set-up-call-analytics.md)

[Utiliser Microsoft Teams rôles d’administrateur pour gérer Teams.](/MicrosoftTeams/using-admin-roles)
