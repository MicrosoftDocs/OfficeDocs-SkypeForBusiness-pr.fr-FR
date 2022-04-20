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
description: Utilisez la télémétrie en temps réel avec des détails sur les appareils, les réseaux et la connectivité pour résoudre les problèmes des utilisateurs lors de Microsoft Teams réunions planifiées.
ms.openlocfilehash: 09c31b7734a849740cf1b0ff5749e4d82c667faf
ms.sourcegitcommit: bf0071417188b33fc23e2a420187da5024d4bd40
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/20/2022
ms.locfileid: "62518726"
---
# <a name="use-real-time-telemetry-to-troubleshoot-poor-meeting-quality"></a>Utiliser la télémétrie en temps réel pour résoudre les problèmes de qualité des réunions

Cet article explique comment utiliser Real-Time Analytics (RTA) pour résoudre les problèmes de qualité de réunion Microsoft Teams médiocre pour les utilisateurs individuels. Vous pouvez accéder à Real-Time Analytics si vous avez l’un des rôles suivants :

- Administrateur Teams
- Spécialiste du support des communications Teams
- Ingénieur du support technique pour les communications Teams

Pour plus d’informations sur Teams rôles d’administrateur, consultez [Utiliser Microsoft Teams rôles d’administrateur pour gérer Teams](/MicrosoftTeams/using-admin-roles).

Real-Time Analytics permet aux administrateurs informatiques d’examiner les réunions planifiées de leurs utilisateurs importants et de voir les problèmes liés à l’audio, à la vidéo, au partage de contenu et au réseau. En tant qu’administrateur, vous pouvez utiliser cette télémétrie pour examiner ces problèmes pendant les réunions et résoudre les problèmes en temps réel.

## <a name="what-is-real-time-analytics"></a>Qu’est-ce que Real-Time Analytics ?

Aujourd’hui, la résolution des problèmes de réunion individuelle est disponible pour Teams administrateurs via [Call Analytics](use-call-analytics-to-troubleshoot-poor-call-quality.md) une fois la réunion terminée. Real-Time Analytics permet aux administrateurs de résoudre les problèmes liés aux réunions planifiées pendant qu’elles sont en cours.

Real-Time Analytics affiche des informations détaillées sur Teams réunions pour chaque utilisateur de votre compte Office 365, mises à jour en temps réel. Il inclut des informations sur les appareils, le réseau, la connectivité, l’audio, la vidéo et les problèmes de partage de contenu, qui aideront les administrateurs à résoudre plus efficacement les problèmes de qualité des appels.

En tant qu’administrateur Teams, vous bénéficiez d’un accès total à toutes les données de télémétrie en temps réel pour chaque utilisateur. En outre, vous pouvez attribuer Azure Active Directory rôles au personnel de soutien. Pour en savoir plus sur ces rôles, consultez [Autoriser le support et le personnel du support](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff) technique.

## <a name="where-to-find-per-user-real-time-troubleshooting-telemetry"></a>Où trouver les données de télémétrie en temps réel par utilisateur

Pour afficher toutes les informations et données de réunion d’un utilisateur, accédez au [centre d’administration Teams](https://admin.teams.microsoft.com). Sous **UtilisateursManage** > , sélectionnez un utilisateur, puis ouvrez l’onglet **Réunions & appels** sur la page de profil de l’utilisateur. Dans **les réunions récentes**, vous verrez une liste des réunions auxquelles l’utilisateur a participé au cours des dernières 24 heures *pour lesquelles des données de télémétrie en temps réel sont disponibles*, y compris les réunions en cours. Si la réunion n’est pas en cours ou n’a pas de données de télémétrie en temps réel, elle s’affiche dans **les réunions précédentes**.

:::image type="content" alt-text="Capture d’écran de la table des réunions récentes." source="media/recent-meetings.png" lightbox="media/recent-meetings.png":::

Pour obtenir des informations supplémentaires sur les participants d’une réunion en cours, y compris leurs statistiques sur l’appareil, le réseau et l’audio, recherchez la réunion dans **les réunions récentes** et sélectionnez le lien sous la colonne **Participants** .

:::image type="content" alt-text="Capture d’écran de la table de détails du participant." source="media/participant-details.png" lightbox="media/participant-details.png":::

Pour examiner les données de télémétrie d’un utilisateur donné pour une réunion en cours, y compris des informations sur l’appareil, le réseau, l’audio, la vidéo et le partage de contenu, sélectionnez **l’ID de réunion**.

:::image type="content" alt-text="Capture d’écran des données de session utilisateur d’analyse des appels." source="media/real-time-telemetry.png" lightbox="media/real-time-telemetry.png":::

## <a name="measures-available-in-real-time-analytics"></a>Mesures disponibles dans Real-Time Analytics

### <a name="audio"></a>Audio
|Nom de la mesure |Unités |Bon seuil |Description |
|:---|:---|:---|:---|
|Jitter |Millisecondes |Moins de 30 ms |Jitter est une mesure de la variation du délai de paquet pour un flux de données. Lorsque cette valeur est trop élevée, l’audio peut devenir agité. | 
|Perte de paquets |Pourcentage |Moins de 5 % |La perte de paquets se produit lorsque les paquets de données ne parviennent pas à atteindre leur destination. Le pourcentage de paquets perdus est basé sur le nombre total de paquets envoyés. |
|Durée des allers-retours |Millisecondes |Moins de 500 ms |Le temps d’aller-retour est le temps nécessaire pour qu’un seul paquet se déplace du client vers le point de terminaison distant et retourne au client. Une durée d’aller-retour élevée peut entraîner des retards dans la lecture du flux. Par exemple, deux personnes d’une réunion parlent involontairement l’une de l’autre en raison du retard. |
|Bitrate |Kilobits par seconde (Kbits/s) |Supérieur à 24 Kbits/s |Débit du flux audio exprimé en kilobits par seconde. |


### <a name="video"></a>Vidéo
|Nom de la mesure |Unités |Bon seuil |Description |
|:---|:---|:---|:---|
|Durée des allers-retours |Millisecondes |Moins de 500 ms |Le temps d’aller-retour est le temps nécessaire pour qu’un seul paquet se déplace du client vers le point de terminaison distant et retourne au client. Une durée d’aller-retour élevée peut entraîner des retards dans la lecture du flux. Par exemple, deux personnes d’une réunion parlent involontairement l’une de l’autre en raison du retard. |
|Bitrate |Mégabits par seconde (Mbits/s) | Informations uniquement |Débit du flux vidéo exprimé en mégabits par seconde. |
|Fréquence d’images (vidéo) |Images par secondes |360p ou mieux : 25-30 FPS <br/> 270 p ou moins : 7-15 FPS |Pour les flux vidéo sortants, le taux d’images (FPS) correspond au nombre d’images par seconde de la vidéo envoyée par le client. Les valeurs inférieures aux valeurs attendues ici peuvent suggérer des contraintes de ressources système, une bande passante réseau insuffisante ou un comportement incorrect des périphériques de capture vidéo. Différentes résolutions ont des plages FPS acceptables différentes. |
|Codec |String | Informations uniquement |Affiche le codec vidéo et le mode de rendu du flux vidéo sortant. (Exemple : H264 SW HW indique un flux vidéo H264 à l’aide du rendu logiciel et matériel.)|
|Solution |Pixels | Informations uniquement |Résolution de la vidéo envoyée. La résolution vidéo sortante est dynamique, en fonction des besoins les plus élevés d’un point de terminaison de la réunion. Un client capable de 1920 x 1 080 vidéo n’envoie que 640 x 360 vidéos si aucun client n’affiche la vidéo de cet utilisateur dans un cadre supérieur à 640 x 360 |


### <a name="application-sharing-vbss"></a>Partage d’applications (VBSS)
|Nom de la mesure |Unités |Bon seuil |Description |
|:---|:---|:---|:---|
|Perte de paquets |Pourcentage |Moins de 5 % |La perte de paquets se produit lorsque les paquets de données ne parviennent pas à atteindre leur destination. Le pourcentage de paquets perdus est basé sur le nombre total de paquets envoyés. |
|Durée des allers-retours |Millisecondes |Moins de 500 ms |Le temps d’aller-retour est le temps nécessaire pour qu’un seul paquet se déplace du client vers le point de terminaison distant et retourne au client. Une durée d’aller-retour élevée peut entraîner des retards dans la lecture du flux. Par exemple, deux personnes d’une réunion parlent involontairement l’une de l’autre en raison du retard. |
|Bitrate |Mégabits par seconde (Mbits/s) | Informations uniquement |Débit du flux VBSS exprimé en mégabits par seconde. |
|Fréquence d’images |Images par seconde (FPS) | Informations uniquement |Pour VBSS, le débit d’images prend en charge le contenu pour garantir que le nombre d’images nécessaire est envoyé pour garantir une bonne expérience tout en évitant d’envoyer des images si elles ne sont pas nécessaires. Par exemple, le partage d’un document texte à l’écran nécessite seulement 1 image par seconde pour produire une bonne expérience, tandis que le partage d’une vidéo ou d’un contenu avec plus d’activité augmente les images par seconde jusqu’à un maximum de 30 FPS pour produire une expérience plus fluide. |
|Codec |String | Informations uniquement |Affiche le codec et le mode de rendu du flux VBSS. (Exemple : H264 SW HW indique un flux H264 VBSS à l’aide du rendu logiciel et matériel.)|
|Solution |Pixels | Informations uniquement |Résolution du flux VBSS envoyé et reçu. |


## <a name="client-platforms-supported-for-real-time-telemetry"></a>Plateformes clientes prises en charge pour la télémétrie en temps réel

- Windows
- macOS
- Linux
- Android
- iOS

> [!NOTE]
> Teams client web (y compris VDI) ne prend pas en charge la remise des données de télémétrie en temps réel.

## <a name="teams-devices-with-support-for-real-time-telemetry"></a>Teams des appareils avec prise en charge de la télémétrie en temps réel

- MTR - Surface Hub
- MTR - affichage Teams
- MTR - Barre de collaboration
- Appareils Téléphone IP

> [!NOTE]
> Les appareils qui ont rejoint la réunion à l’aide de solutions CVI (Cloud Video Interop) ne sont pas pris en charge dans Real-Time Analytics.


## <a name="limitations"></a>Limites

- Les données de télémétrie en temps réel sont disponibles uniquement pour les réunions planifiées. Pour les réunions ad hoc telles que les réunions Meet Now, PSTN, les appels 1:1 et les appels de groupe, la télémétrie en temps réel n’est pas disponible.
- La télémétrie en temps réel est disponible uniquement pour les présentateurs d’événements en direct planifiés. Il n’est actuellement pas disponible pour les participants aux événements en direct.
- Les données de télémétrie en temps réel sont disponibles pour une réunion dans **le cadre de réunions récentes** pendant 24 heures après la fin de la réunion. Après 24 heures, vous ne pouvez pas accéder aux données et la réunion passe aux **réunions précédentes**. Si une réunion dure plus de 3 heures, les données de télémétrie en temps réel ne sont disponibles que pour les *3 dernières heures*.
- La télémétrie n’est pas disponible en temps réel lors de l’utilisation d’anciennes versions de Teams. Si aucune télémétrie n’est disponible, essayez de mettre à jour votre client.
- Si des participants externes ou des utilisateurs anonymes participent à une réunion, leur nom complet s’affiche comme **étant indisponible** pour conserver la confidentialité entre locataires.

## <a name="related-topics"></a>Voir aussi

[Configurer l’analytique des appels par utilisateur](set-up-call-analytics.md)

[Utilisez Microsoft Teams rôles d’administrateur pour gérer Teams](/MicrosoftTeams/using-admin-roles).
