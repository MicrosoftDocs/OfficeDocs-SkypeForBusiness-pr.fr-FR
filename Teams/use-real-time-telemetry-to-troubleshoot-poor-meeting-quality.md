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
description: Utilisez la télémétrie en temps réel avec des détails sur les appareils, les réseaux et la connectivité pour résoudre les problèmes des utilisateurs lors des réunions planifiées de Microsoft Teams.
ms.openlocfilehash: c7bc5ee0415a289782cad1dd7daa5c13bdaf7364
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2022
ms.locfileid: "66494721"
---
# <a name="use-real-time-telemetry-to-troubleshoot-poor-meeting-quality"></a>Utiliser la télémétrie en temps réel pour résoudre les problèmes de qualité des réunions

Cet article explique comment utiliser Real-Time Analytics (RTA) pour résoudre les problèmes de mauvaise qualité des réunions Microsoft Teams pour les utilisateurs individuels. Vous pouvez accéder à Real-Time Analytics si vous avez l’un des rôles suivants :

- Administrateur Teams
- Spécialiste du support des communications Teams
- Ingénieur du support technique pour les communications Teams

Pour plus d’informations sur les rôles d’administrateur Teams, consultez [Utiliser les rôles d’administrateur Microsoft Teams pour gérer Teams](/MicrosoftTeams/using-admin-roles).

Real-Time Analytics permet aux administrateurs informatiques d’examiner les réunions planifiées de leurs utilisateurs importants et de voir les problèmes liés à l’audio, à la vidéo, au partage de contenu et au réseau. En tant qu’administrateur, vous pouvez utiliser cette télémétrie pour examiner ces problèmes pendant les réunions et résoudre les problèmes en temps réel.

## <a name="what-is-real-time-analytics"></a>Qu’est-ce que Real-Time Analytics ?

Aujourd’hui, la résolution des problèmes des réunions individuelles est disponible pour les administrateurs Teams via [Call Analytics](use-call-analytics-to-troubleshoot-poor-call-quality.md) une fois la réunion terminée. Real-Time Analytics permet aux administrateurs de résoudre les problèmes liés aux réunions planifiées pendant qu’elles sont en cours.

Real-Time Analytics affiche des informations détaillées sur les réunions Teams pour chaque utilisateur de votre compte Office 365, mises à jour en temps réel. Il inclut des informations sur les appareils, le réseau, la connectivité, l’audio, la vidéo et les problèmes de partage de contenu, qui aideront les administrateurs à résoudre plus efficacement les problèmes de qualité des appels.

En tant qu’administrateur Teams, vous bénéficiez d’un accès complet à toutes les données de télémétrie en temps réel pour chaque utilisateur. En outre, vous pouvez attribuer des rôles Azure Active Directory au personnel de support. Pour en savoir plus sur ces rôles, consultez [Autoriser le support et le personnel du support](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff) technique.

## <a name="where-to-find-per-user-real-time-troubleshooting-telemetry"></a>Où trouver les données de télémétrie en temps réel par utilisateur

Pour afficher toutes les informations et données de réunion d’un utilisateur, accédez au [Centre d’administration Teams](https://admin.teams.microsoft.com). Sous **Gérer** > **les utilisateurs**, sélectionnez un utilisateur, puis ouvrez l’onglet **Réunions & appels** sur la page de profil de l’utilisateur. Dans **les réunions récentes**, vous verrez une liste des réunions auxquelles l’utilisateur a participé au cours des dernières 24 heures *pour lesquelles des données de télémétrie en temps réel sont disponibles*, y compris les réunions en cours. Si la réunion n’est pas en cours ou n’a pas de données de télémétrie en temps réel, elle s’affiche dans **les réunions précédentes**.

:::image type="content" alt-text="Capture d’écran de la table des réunions récentes." source="media/recent-meetings.png" lightbox="media/recent-meetings.png":::

Pour obtenir des informations supplémentaires sur les participants d’une réunion en cours, y compris leurs statistiques sur l’appareil, le réseau et l’audio, recherchez la réunion dans **les réunions récentes** et sélectionnez le lien sous la colonne **Participants** .

:::image type="content" alt-text="Capture d’écran de la table de détails du participant." source="media/participant-details-edit.png" lightbox="media/participant-details-edit.png":::

Pour examiner les données de télémétrie d’un utilisateur donné pour une réunion en cours, y compris des informations sur l’appareil, le réseau, l’audio, la vidéo et le partage de contenu, sélectionnez **l’ID de réunion**.

:::image type="content" alt-text="Capture d’écran des données de session utilisateur d’analyse des appels." source="media/real-time-telemetry-edit.png" lightbox="media/real-time-telemetry-edit.png":::

## <a name="details-and-measures-available-in-real-time-analytics"></a>Détails et mesures disponibles dans Real-Time Analytics

### <a name="device-information"></a>Informations sur l’appareil
| Nom | Description | Raisons possibles de valeurs vides|
|:---|:---|:---|
| Périphérique de capture audio | Nom de l’appareil de capture audio (par exemple, microphone) utilisé | Il se peut que le système n’ait pas de nom associé à l’appareil (par exemple, bureau à distance ou appareil « Audio distant » de la machine virtuelle)  |
| Périphérique de rendu audio | Nom de l’appareil de rendu audio (par exemple, haut-parleurs ou écouteurs) utilisé | Il se peut que le système n’ait pas de nom associé à l’appareil (par exemple, bureau à distance ou appareil « Audio distant » de la machine virtuelle)  |
| Appareil de capture vidéo | Nom de l’appareil de capture vidéo utilisé | L’utilisateur n’envoie pas de vidéo à partir du point de terminaison surveillé |

### <a name="connectivity-information"></a>Informations de connectivité
| Mesure | Unités / Valeurs possibles | Description | Raisons possibles de valeurs vides|
|:---|:---|:---|:---|
| Type de réseau | &bull; Ethernet <br/> &bull; Wi-Fi | Type de connexion réseau utilisée | |
| Wi-Fi force | &bull; Excellent : -50dBm ou supérieur <br/> &bull; Bon : -51 dBm à -64 dBm<br/> &bull; Médiocre : -65 dBm ou inférieur | Force de la connexion Wi-Fi actuelle de l’utilisateur | L’utilisateur n’est pas connecté à Wi-Fi |
| canal Wi-Fi | Entier | Canal sur lequel le point d’accès du réseau Wi-Fi diffuse | L’utilisateur n’est pas connecté à Wi-Fi |
| Type physique | String <br/> &bull; Exemple : 802.11ac | Type d’infrastructure sans fil utilisé | L’utilisateur n’est pas connecté à Wi-Fi |
| bande Wi-Fi | 2,4 GHz ou 5 GHz | Wi-Fi bande à laquelle l’utilisateur est connecté | L’utilisateur n’est pas connecté à Wi-Fi |
| Lieu | String | Pays dans lequel se trouve l’utilisateur | Les informations d’emplacement de l’utilisateur sont bloquées ou indisponibles |
| Adresse IP locale | String (IP:Port) | Adresse IP locale du point de terminaison de l’utilisateur et du port multimédia | |
| Adresse IP réflexive du serveur | String (IP:Port) | Adresse IP publique du point de terminaison de l’utilisateur et du port multimédia | |
| Type de connectivité | UDP ou TCP | Protocole de couche de transport en service ; UDP est préféré pour les médias en temps réel | |

### <a name="user-signals"></a>Signaux utilisateur
Les signaux utilisateur identifient quand un utilisateur participe activement à l’appel, ne parle pas, mais est désactivé ou est désactivé. Actuellement, les signaux utilisateur sont uniquement disponibles pour l’audio.

| Modalité | Valeurs possibles | Description |
|:---|:---|:---|
| Audio | &bull; Non activé, participant parlant <br/> &bull; Non activé, ne parlant pas <br/> &bull; Coupé | Indique le comportement de l’utilisateur pour la partie audio de l’appel  |


### <a name="audio"></a>Audio
|Nom de la mesure |Unités |Bon seuil |Description |
|:---|:---|:---|:---|
|Jitter |Millisecondes |Moins de 30 ms |Jitter est une mesure de la variation du délai de paquet pour un flux de données. Lorsque cette valeur est trop élevée, l’audio peut devenir agité. | 
|Perte de paquets |Pourcentage |Moins de 5 % |La perte de paquets se produit lorsque les paquets de données ne parviennent pas à atteindre leur destination. Le pourcentage de paquets perdus est basé sur le nombre total de paquets envoyés. |
|Durée des allers-retours |Millisecondes |Moins de 500 ms |Le temps d’aller-retour est le temps nécessaire pour qu’un seul paquet se déplace du client vers le point de terminaison distant et retourne au client. Une durée d’aller-retour élevée peut entraîner des retards dans la lecture du flux. Par exemple, deux personnes d’une réunion parlent involontairement l’une de l’autre en raison du retard. S’affiche uniquement pour l’audio sortant. |
|Bitrate |Kilobits par seconde (Kbits/s) |Supérieur à 24 Kbits/s |Débit du flux audio exprimé en kilobits par seconde. |
| Codec | String <br/> &bull; Exemple : SATIN | Informations uniquement | Affiche le codec audio envoyé et reçu. Un codec différent peut être reçu que celui envoyé. |


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
> Le client web Teams (y compris VDI) ne prend pas en charge la distribution des données de télémétrie en temps réel.

## <a name="teams-devices-with-support-for-real-time-telemetry"></a>Appareils Teams avec prise en charge de la télémétrie en temps réel

- MTR - Surface Hub
- MTR - Affichage Teams
- MTR - Barre de collaboration
- Appareils IP Phone

> [!NOTE]
> Les appareils qui ont rejoint la réunion à l’aide de solutions CVI (Cloud Video Interop) ne sont pas pris en charge dans Real-Time Analytics.


## <a name="limitations"></a>Limites

- La télémétrie en temps réel est disponible uniquement pour les réunions planifiées et meet now. Pour les appels RTC, les appels 1:1 et les appels de groupe, la télémétrie en temps réel n’est pas disponible.
- La télémétrie en temps réel est disponible uniquement pour les présentateurs d’événements en direct planifiés. Il n’est actuellement pas disponible pour les participants aux événements en direct.
- Les données de télémétrie en temps réel sont disponibles pour une réunion dans **le cadre de réunions récentes** pendant 24 heures après la fin de la réunion. Après 24 heures, vous ne pouvez pas accéder aux données et la réunion passe aux **réunions précédentes**. Si une réunion dure plus de 3 heures, les données de télémétrie en temps réel ne sont disponibles que pour les *3 dernières heures*.
- La télémétrie n’est pas disponible en temps réel lors de l’utilisation d’anciennes versions de Teams. Si aucune télémétrie n’est disponible, essayez de mettre à jour votre client.
- Si des participants externes ou des utilisateurs anonymes participent à une réunion, leur nom complet s’affiche comme **étant indisponible** pour conserver la confidentialité entre locataires.

## <a name="related-topics"></a>Sujets associés

[Configurer l’analytique des appels par utilisateur](set-up-call-analytics.md)

[Utilisez des rôles d’administrateur Microsoft Teams pour gérer Teams](/MicrosoftTeams/using-admin-roles).
