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
ms.openlocfilehash: 199eac099e23e8f8f0d96393484c4594763bb47a
ms.sourcegitcommit: 12044ab8b2e79a7b23bf9a0918ae070925d21f3d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/10/2021
ms.locfileid: "61401998"
---
# <a name="use-real-time-telemetry-to-troubleshoot-poor-meeting-quality"></a>Utiliser la télémétrie en temps réel pour résoudre les problèmes de qualité des réunions

Cet article explique comment utiliser RTA (Real-Time Analytics) pour résoudre des problèmes de qualité Microsoft Teams réunion pour des utilisateurs individuels. Vous pouvez accéder à Real-Time Analytics si vous avez l’un des rôles suivants :

- Administrateur Teams
- Teams du support technique pour les communications
- Ingénieur du support technique pour les communications Teams

Pour plus d’informations sur Teams rôles d’administrateur, voir Utiliser Microsoft Teams rôles d’administrateur [pour gérer Teams.](/MicrosoftTeams/using-admin-roles)

Real-Time Analytics permet aux administrateurs informatiques d’examiner les réunions programmées de leurs utilisateurs importants et de voir les problèmes audio, vidéo, de partage de contenu et de réseau. En tant qu’administrateur, vous pouvez utiliser cette télémétrie pour examiner ces problèmes pendant les réunions et résoudre les problèmes en temps réel.

## <a name="what-is-real-time-analytics"></a>Qu’est-Real-Time Analyse de données ?

Aujourd’hui, la résolution des problèmes de réunion individuelle est disponible pour Teams administrateurs via [l’outil d’analyse](use-call-analytics-to-troubleshoot-poor-call-quality.md) des appels une fois la réunion terminée. Real-Time Analytics permet aux administrateurs de dépanner les réunions programmées en cours.

Real-Time Analytics affiche des informations détaillées sur Teams réunions pour chaque utilisateur dans votre Office 365 utilisateur, mises à jour en temps réel. Il inclut des informations sur les périphériques, le réseau, la connectivité, l’audio, la vidéo et les problèmes de partage de contenu, qui aideront les administrateurs à résoudre les problèmes de qualité des appels de façon plus efficace.

En tant qu Teams administrateur de services, vous avez un accès total à toutes les données de télémétrie en temps réel pour chaque utilisateur. De plus, vous pouvez attribuer des rôles Azure Active Directory au personnel de support technique. Pour en savoir plus sur ces rôles, voir [Accorder l’autorisation au support technique et au personnel de support technique.](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff)

## <a name="where-to-find-per-user-real-time-troubleshooting-telemetry"></a>Où trouver la résolution des problèmes de télémétrie en temps réel par utilisateur

Pour voir toutes les informations et données de réunion d’un utilisateur, rendez-vous dans le [Teams d’administration.](https://admin.teams.microsoft.com) Sous **Gérer les**  >  **utilisateurs,** sélectionnez un utilisateur, puis ouvrez l’onglet & **appels** sur la page de profil de l’utilisateur. Sous Réunions **récentes,** vous verrez la liste des réunions que l’utilisateur a participé au cours des 24 dernières heures pour lesquelles la télémétrie en temps réel est *disponible,* y compris les réunions en cours. Si la réunion n’est pas en cours ou ne comprend pas de données de télémétrie en temps réel, elle s’affiche dans **réunions passées.**

:::image type="content" alt-text="Capture d’écran de la table réunions récentes." source="media/recent-meetings.png" lightbox="media/recent-meetings.png":::

Pour obtenir des informations supplémentaires sur les participants d’une réunion en cours, notamment les statistiques sur l’appareil, le réseau et l’audio, recherchez la réunion dans Réunions **récentes** et sélectionnez le lien sous la colonne **Participants.**

:::image type="content" alt-text="Capture d’écran du tableau des détails des participants." source="media/participant-details.png" lightbox="media/participant-details.png":::

Pour examiner la télémétrie d’un utilisateur donné pour une réunion en cours, y compris les informations sur l’appareil, le réseau, l’audio, la vidéo et les détails du partage de contenu, sélectionnez **l’ID** de réunion.

:::image type="content" alt-text="Capture d’écran des données de session de l’utilisateur d’analyse des appels." source="media/real-time-telemetry.png" lightbox="media/real-time-telemetry.png":::

## <a name="measures-available-in-real-time-analytics"></a>Mesures disponibles dans Real-Time Analytics

|Nom de la mesure |Unités |Bon seuil |Description |
|:---|:---|:---|:---|
|Jitter |Millisecondes |Moins de 30 ms |La gigue est une mesure de la variation de délai des paquets pour un flux de données. Lorsque ce niveau est trop élevé, l’audio peut être haché. | 
|Perte de paquets |Pourcentage |Inférieur à 5 % |La perte de paquets se produit lorsque les paquets de données n’atteignent pas leur destination. Le pourcentage de perte de paquets est basé sur le nombre total de paquets envoyés. |
|Durée de l’aller-retour |Millisecondes |Moins de 500 ms |La durée des allers-retours est la durée du trajet d’un paquet entre le client et le point de terminaison distant, puis de revenir au client. Une durée élevée des allers-retours peut entraîner des retards dans la lecture des flux. Par exemple, deux personnes dans une réunion parlent involontairement l’une sur l’autre en raison d’un retard. |
|Bitrate (audio) |Kilo-bits par seconde (Kbits/s) |Supérieur à 24 Kbits/s |Débit du flux audio exprimé en kilobits par seconde. |
|Bitrate (partage d'& vidéo) |Mégabits par seconde (Mbits/s) | Informations uniquement |Débit du flux vidéo exprimé en mégabits par seconde. |
|Fréquence d’images (vidéo) |Images par secondes |360p ou meilleure : 25-30 FPS <br/> 270p ou une valeur inférieure : 7-15 FPS |Pour les flux vidéo sortants, la fréquence d’images (FPS) est le nombre d’images par seconde de vidéo que le client envoie. Les valeurs inférieures aux valeurs prévues peuvent indiquer des contraintes de ressources système, une bande passante réseau insuffisante ou des périphériques de capture vidéo qui ne sont pas connectés. Les différentes résolutions ont différentes plages de fps acceptables. |
|Fréquence d’images (partage d’application) |Images par seconde (FPS) |Informations uniquement |Pour le partage d’application, la fréquence d’images est un contenu qui permet de s’assurer qu’un nombre d’images aussi élevé que nécessaire est envoyé pour garantir une bonne expérience tout en évitant d’envoyer des cadres si nécessaire. Par exemple, le partage d’un document texte à l’écran ne nécessite qu’une image par seconde pour obtenir une expérience agréable, tandis que le partage d’une vidéo ou d’un contenu avec une activité plus importante augmente les images par seconde au maximum de 30 images par seconde pour que l’expérience soit plus fluide. |


## <a name="client-platforms-supported-for-real-time-telemetry"></a>Plateformes clientes prise en charge pour la télémétrie en temps réel

- Windows
- macOS
- Linux
- Android
- iOS

> [!NOTE]
> Teams client web (Y compris VDI) ne prend pas en charge la télémétrie en temps réel.

## <a name="teams-devices-with-support-for-real-time-telemetry"></a>Teams appareils avec prise en charge de la télémétrie en temps réel

- MTR - Surface Hub
- MTR - Teams Display
- MTR - Barre de collaboration
- Appareils IP Téléphone ip

> [!NOTE]
> Les périphériques qui ont rejoint la réunion à l’aide des solutions Cloud Video Interop (CVI) ne sont pas pris en charge dans Real-Time Analytics.


## <a name="limitations"></a>Limites

- La télémétrie en temps réel est disponible uniquement pour les réunions prévues. Pour les réunions ad hoc telles que Conférence maintenant, PSTN, appels 1:1 et appels de groupe, la télémétrie en temps réel n’est pas disponible.
- La télémétrie en temps réel n’est disponible que pour les présentateurs d’un événement en direct programmé. Elle n’est actuellement pas disponible pour les participants à un événement en direct.
- Les données de télémétrie en temps réel sont disponibles pour une réunion sous Réunions **récentes** 24 heures après la fin de la réunion. Au bout de 24 heures, vous ne pouvez plus accéder aux données et la réunion passe **aux réunions passées.** Si une réunion dure plus de 3 heures, la télémétrie en temps réel sera disponible uniquement pendant *les 3 dernières heures.*
- La télémétrie n’est pas disponible en temps réel lorsque vous utilisez des versions antérieures de Teams. Si aucune télémétrie n’est disponible, essayez de mettre à jour votre client.
- Si des participants externes ou des utilisateurs  anonymes rejoignent une réunion, leur nom d’affichage s’affiche comme indisponible pour conserver la confidentialité entre clients.

## <a name="related-topics"></a>Rubriques connexes

[Configurer l’analyse des appels par utilisateur](set-up-call-analytics.md)

[Utilisez Microsoft Teams rôles d’administrateur pour gérer Teams.](/MicrosoftTeams/using-admin-roles)
