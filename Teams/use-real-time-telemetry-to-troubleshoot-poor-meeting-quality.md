---
title: Utiliser la télémétrie en temps réel pour résoudre les problèmes de qualité des réunions
author: CarolynRowe
ms.author: crowe
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
description: Utilisez la télémétrie en temps réel avec des détails sur les appareils, les réseaux et la connectivité pour résoudre les problèmes des utilisateurs avec les réunions planifiées Microsoft Teams.
ms.openlocfilehash: bbda6d34a990ad810b22ce1742ab60a886295a6a
ms.sourcegitcommit: feb9b7d10e38f5a629ee9202b5aaec5beef4de9b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/10/2022
ms.locfileid: "69343277"
---
# <a name="use-real-time-telemetry-to-troubleshoot-poor-meeting-quality"></a>Utiliser la télémétrie en temps réel pour résoudre les problèmes de qualité des réunions

Cet article explique comment utiliser Real-Time Analytics (RTA) pour résoudre les problèmes de mauvaise qualité de réunion Microsoft Teams pour les utilisateurs individuels. Vous pouvez accéder à Real-Time Analytics si vous disposez de l’un des rôles suivants :

- Administrateur Teams
- Spécialiste du support des communications Teams
- Ingénieur du support technique pour les communications Teams

Pour plus d’informations sur les rôles d’administrateur Teams, consultez [Utiliser Microsoft rôles d’administrateur Teams pour gérer Teams](/MicrosoftTeams/using-admin-roles).

Real-Time Analytics permet aux administrateurs informatiques d’examiner les réunions planifiées de leurs utilisateurs importants et de voir les problèmes liés à l’audio, à la vidéo, au partage de contenu et au réseau. En tant qu’administrateur, vous pouvez utiliser ces données de télémétrie pour examiner ces problèmes pendant les réunions et résoudre les problèmes en temps réel.

## <a name="what-is-real-time-analytics"></a>Qu’est-ce que Real-Time Analytics ?

Aujourd’hui, la résolution des problèmes de réunion individuelle est disponible pour les administrateurs Teams via [l’analyse des appels](use-call-analytics-to-troubleshoot-poor-call-quality.md) après la fin de la réunion. Real-Time Analytics permet aux administrateurs de résoudre les problèmes liés aux réunions planifiées pendant qu’elles sont en cours.

Real-Time Analytics affiche des informations détaillées sur les réunions Teams pour chaque utilisateur de votre compte Office 365, mises à jour en temps réel. Il inclut des informations sur les appareils, le réseau, la connectivité, l’audio, la vidéo et les problèmes de partage de contenu, ce qui aidera les administrateurs à résoudre les problèmes de qualité des appels plus efficacement.

En tant qu’administrateur Teams, vous bénéficiez d’un accès complet à toutes les données de télémétrie en temps réel pour chaque utilisateur. En outre, vous pouvez attribuer des rôles Azure Active Directory au personnel du support technique. Pour en savoir plus sur ces rôles, consultez [Accorder l’autorisation au personnel du support technique et du support technique](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff).

## <a name="where-to-find-per-user-real-time-troubleshooting-telemetry"></a>Où trouver les données de télémétrie de résolution des problèmes en temps réel par utilisateur

Pour afficher toutes les informations et données de réunion d’un utilisateur, accédez au [Centre d’administration Teams](https://admin.teams.microsoft.com). Sous **Utilisateurs** > **Gérer les utilisateurs**, sélectionnez un utilisateur et ouvrez l’onglet **Réunions & appels** sur la page de profil de l’utilisateur. Sous **Réunions récentes**, vous verrez une liste des réunions auxquelles l’utilisateur a participé au cours des dernières 24 heures *pour lesquelles la télémétrie en temps réel est disponible*, y compris les réunions en cours. Si la réunion n’est pas en cours ou n’a pas de données de télémétrie en temps réel, elle s’affiche dans **réunions précédentes**.

:::image type="content" alt-text="Capture d’écran du tableau des réunions récentes." source="media/recent-meetings.png" lightbox="media/recent-meetings.png":::

> [!NOTE]
> Pour qu’une réunion s’affiche sous « Réunions récentes », un administrateur Teams doit avoir cliqué sur la réunion dans Real-Time Analytics pendant que la réunion était en cours pour commencer le flux de télémétrie client en temps réel.


Pour obtenir des informations supplémentaires sur les participants d’une réunion en cours, notamment leurs statistiques d’appareil, de réseau et audio, recherchez la réunion dans **Réunions récentes** et sélectionnez le lien sous la colonne **Participants** .

:::image type="content" alt-text="Capture d’écran de la table des détails du participant." source="media/participant-details-edit.png" lightbox="media/participant-details-edit.png":::

Pour examiner les données de télémétrie d’un utilisateur donné pour une réunion en cours, notamment des informations sur l’appareil, le réseau, l’audio, la vidéo et le partage de contenu, sélectionnez **l’ID de réunion**.

:::image type="content" alt-text="Capture d’écran des données de session utilisateur d’analyse des appels." source="media/real-time-telemetry-edit.png" lightbox="media/real-time-telemetry-edit.png":::

## <a name="details-and-measures-available-in-real-time-analytics"></a>Détails et mesures disponibles dans Real-Time Analytics

### <a name="device-information"></a>Informations sur l’appareil
| Nom | Description | Raisons possibles pour les valeurs vides|
|:---|:---|:---|
| Périphérique de capture audio | Nom du périphérique de capture audio (par exemple : microphone) en cours d’utilisation | Il se peut que le système n’ait pas de nom associé à l’appareil (par exemple, bureau à distance ou appareil « Audio distant ») de la machine virtuelle)  |
| Périphérique de rendu audio | Nom du périphérique de rendu audio (par exemple : haut-parleurs ou casque) en cours d’utilisation | Il se peut que le système n’ait pas de nom associé à l’appareil (par exemple, bureau à distance ou appareil « Audio distant ») de la machine virtuelle)  |
| Périphérique de capture vidéo | Nom de l’appareil de capture vidéo utilisé | L’utilisateur n’envoie pas de vidéo à partir du point de terminaison surveillé |

### <a name="connectivity-information"></a>Informations de connectivité
| Mesure | Unités / Valeurs possibles | Description | Raisons possibles pour les valeurs vides|
|:---|:---|:---|:---|
| Type de réseau | &bull; Ethernet <br/> &bull; Wi-Fi | Type de connexion réseau utilisée | |
| Wi-Fi force | &bull; Excellent : -50 dBm ou supérieur <br/> &bull; Bon : -51 dBm à -64 dBm<br/> &bull; Médiocre : -65 dBm ou inférieur | Force de la connexion Wi-Fi actuelle de l’utilisateur | L’utilisateur n’est pas connecté à Wi-Fi |
| canal Wi-Fi | Entier | Canal sur lequel le point d’accès du réseau Wi-Fi diffuse | L’utilisateur n’est pas connecté à Wi-Fi |
| Type physique | String <br/> &bull; Exemple : 802.11ac | Type d’infrastructure sans fil utilisé | L’utilisateur n’est pas connecté à Wi-Fi |
| Wi-Fi bande | 2,4 GHz ou 5 GHz | Wi-Fi bande à laquelle l’utilisateur est connecté | L’utilisateur n’est pas connecté à Wi-Fi |
| Lieu | String | Pays dans lequel se trouve l’utilisateur | Les informations d’emplacement de l’utilisateur sont bloquées ou indisponibles |
| Adresse IP locale | Chaîne (IP:Port) | Adresse IP locale du point de terminaison de l’utilisateur et du port multimédia | |
| Adresse IP réflexive du serveur | Chaîne (IP:Port) | Adresse IP publique du point de terminaison de l’utilisateur et du port multimédia | |
| Type de connectivité | UDP ou TCP | Protocole de couche de transport en cours d’utilisation ; UDP est préféré pour les médias en temps réel | |

### <a name="user-signals"></a>Signaux utilisateur
Les signaux utilisateur identifient lorsqu’un utilisateur participe activement à l’appel, qu’il ne parle pas, mais qu’il n’est pas activé ou qu’il est désactivé. Actuellement, les signaux utilisateur ne sont disponibles que pour l’audio.

| Modalité | Valeurs possibles | Description |
|:---|:---|:---|
| Audio | &bull; Non activé, participant parlant <br/> &bull; Non activé, ne parlant pas <br/> &bull; Coupé | Indique le comportement de l’utilisateur pour la partie audio de l’appel  |


### <a name="audio"></a>Audio
|Nom de la mesure |Unités |Seuil correct |Description |
|:---|:---|:---|:---|
|Jitter |Millisecondes |Moins de 30 ms |La gigue est une mesure de la variation du délai de paquet pour un flux de données. Lorsque cette valeur est trop élevée, l’audio peut devenir haché. | 
|Perte de paquets |Pourcentage |Moins de 5 % |La perte de paquets se produit lorsque les paquets de données ne parviennent pas à leur destination. Le pourcentage de paquets perdus est basé sur le nombre total de paquets envoyés. |
|Durée aller-retour |Millisecondes |Moins de 500 ms |Le temps aller-retour est le temps nécessaire pour qu’un paquet unique se déplace du client au point de terminaison distant et retourne au client. Un temps d’aller-retour élevé peut entraîner des retards dans la lecture du flux. Un exemple de cela est lorsque deux personnes d’une réunion parlent involontairement l’une sur l’autre en raison du retard. Affiché pour l’audio sortant uniquement. |
|Bitrate |Kilobits par seconde (Kbits/s) |Supérieur à 24 Kbits/s |Débit du flux audio exprimé en kilobits par seconde. |
| Codec | String <br/> &bull; Exemple : SATIN | Informations uniquement | Affiche le codec audio envoyé et reçu. Un codec différent de celui envoyé peut être reçu. |


### <a name="video"></a>Vidéo
|Nom de la mesure |Unités |Seuil correct |Description |
|:---|:---|:---|:---|
|Durée aller-retour |Millisecondes |Moins de 500 ms |Le temps aller-retour est le temps nécessaire pour qu’un paquet unique se déplace du client au point de terminaison distant et retourne au client. Un temps d’aller-retour élevé peut entraîner des retards dans la lecture du flux. Un exemple de cela est lorsque deux personnes d’une réunion parlent involontairement l’une sur l’autre en raison du retard. |
|Bitrate |Mégabits par seconde (Mbits/s) | Informations uniquement |Débit du flux vidéo exprimé en mégabits par seconde. |
|Fréquence d’images (vidéo) |Images par secondes |360p ou plus : 25-30 FPS <br/> 270p ou moins : 7-15 FPS |Pour les flux vidéo sortants, la fréquence d’images (FPS) est le nombre d’images par seconde de vidéo que le client envoie. Des valeurs inférieures aux attentes ici peuvent suggérer des contraintes de ressources système, une bande passante réseau insuffisante ou un comportement incorrect des appareils de capture vidéo. Différentes résolutions ont des plages FPS acceptables différentes. |
|Codec |String | Informations uniquement |Affiche le codec vidéo et le mode de rendu du flux vidéo sortant. (Exemple : H264 SW HW indique un flux vidéo H264 utilisant le rendu logiciel et matériel.)|
|Solution |Pixels | Informations uniquement |Résolution de la vidéo envoyée. La résolution vidéo sortante est dynamique, basée sur les exigences les plus élevées d’un point de terminaison de la réunion. Un client capable de 1920 x 1080 vidéos n’envoie que 640 x 360 vidéos si aucun client n’affiche la vidéo de cet utilisateur dans une image supérieure à 640 x 360 |


### <a name="application-sharing-vbss"></a>Partage d’applications (VBSS)
|Nom de la mesure |Unités |Seuil correct |Description |
|:---|:---|:---|:---|
|Perte de paquets |Pourcentage |Moins de 5 % |La perte de paquets se produit lorsque les paquets de données ne parviennent pas à leur destination. Le pourcentage de paquets perdus est basé sur le nombre total de paquets envoyés. |
|Durée aller-retour |Millisecondes |Moins de 500 ms |Le temps aller-retour est le temps nécessaire pour qu’un paquet unique se déplace du client au point de terminaison distant et retourne au client. Un temps d’aller-retour élevé peut entraîner des retards dans la lecture du flux. Un exemple de cela est lorsque deux personnes d’une réunion parlent involontairement l’une sur l’autre en raison du retard. |
|Bitrate |Mégabits par seconde (Mbits/s) | Informations uniquement |Débit du flux VBSS exprimé en mégabits par seconde. |
|Fréquence d’images |Images par seconde (FPS) | Informations uniquement |Pour VBSS, la fréquence d’images prend en charge le contenu pour garantir que autant d’images que nécessaire sont envoyées afin de garantir une bonne expérience tout en évitant d’envoyer des images si elles ne sont pas nécessaires. Par exemple, le partage d’un document texte à l’écran nécessite seulement 1 image par seconde pour produire une bonne expérience, tandis que le partage d’une vidéo ou d’un contenu avec plus d’activité augmente les images par seconde jusqu’à un maximum de 30 images par seconde pour produire une expérience plus fluide. |
|Codec |String | Informations uniquement |Affiche le codec et le mode de rendu du flux VBSS. (Exemple : H264 SW HW indique un flux VBSS H264 utilisant le rendu logiciel et matériel.)|
|Solution |Pixels | Informations uniquement |Résolution du flux VBSS envoyé et reçu. |


## <a name="client-platforms-supported-for-real-time-telemetry"></a>Plateformes clientes prises en charge pour la télémétrie en temps réel

- Windows
- macOS
- Linux
- Android
- iOS

> [!NOTE]
> Le client Web Teams (y compris VDI) ne prend pas en charge la livraison de données de télémétrie en temps réel.

## <a name="teams-devices-with-support-for-real-time-telemetry"></a>Appareils Teams avec prise en charge de la télémétrie en temps réel

- Affichage teams
- Téléphone Teams
- salles Teams
- salles Teams sur Surface Hub

> [!NOTE]
> Les appareils qui ont rejoint la réunion à l’aide de solutions CVI (Cloud Video Interop) ne sont pas pris en charge dans Real-Time Analytics.


## <a name="limitations"></a>Limites

- L’abonnement à la télémétrie en temps réel n’est pas automatique pour toutes les réunions et doit être démarré par un administrateur Teams pendant que la réunion est en cours.
- La télémétrie en temps réel ne sera disponible que pour les points de terminaison pris en charge par une réunion à partir du point où l’administrateur a cliqué pour la première fois sur la réunion en cours dans Real-Time Analytics.
- La télémétrie en temps réel est disponible uniquement pour les réunions planifiées et Les réunions maintenant. Pour les appels RTC, 1:1 et les appels de groupe, la télémétrie en temps réel n’est pas disponible.
- La télémétrie en temps réel est disponible uniquement pour les présentateurs d’événements en direct planifiés. Il n’est actuellement pas disponible pour les participants à l’événement en direct.
- Les données de télémétrie en temps réel sont disponibles pour une réunion sous **Réunions récentes** pendant 24 heures après la fin de la réunion. Après 24 heures, vous ne pouvez plus accéder aux données et la réunion passe aux **réunions précédentes**. Si une réunion dure plus de 3 heures, la télémétrie en temps réel ne sera disponible que pour les *3 dernières heures*.
- La télémétrie n’est pas disponible en temps réel lors de l’utilisation d’anciennes versions de Teams. Si aucune télémétrie n’est disponible, essayez de mettre à jour votre client.
- Si des participants externes ou des utilisateurs anonymes rejoignent une réunion, leur nom d’affichage s’affiche comme **étant indisponible** pour conserver la confidentialité inter-locataires.

> [!NOTE]
> Dans le cadre d’une préversion publique à durée limitée, les données de télémétrie en temps réel sont actuellement disponibles pendant **7 jours** après la fin d’une réunion. Une fois la préversion terminée, seuls les locataires disposant d’une licence de module complémentaire Communications avancées disposeront de données de télémétrie disponibles pour la période prolongée de 7 jours. Tous les autres locataires seront soumis aux limites mentionnées ci-dessus.

## <a name="related-topics"></a>Rubriques connexes

[Configurer l’analytique des appels par utilisateur](set-up-call-analytics.md)

[Utilisez Microsoft rôles d’administrateur Teams pour gérer Teams](/MicrosoftTeams/using-admin-roles).
