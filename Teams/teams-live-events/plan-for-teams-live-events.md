---
title: Planifier des événements en direct dans Microsoft Teams
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
description: Découvrez les facteurs à prendre en compte avant de configurer des événements en direct dans Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 14827e6ded282c113e56dd3fa567b4c7835bbf23
ms.sourcegitcommit: 9d9376c6e5e6d79e33ba54fb8ce87509a2f57754
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/17/2019
ms.locfileid: "35013028"
---
# <a name="plan-for-live-events-in-microsoft-teams"></a>Planifier des événements en direct dans Microsoft Teams

Lorsque vous planifiez des événements en direct teams pour organiser des réunions de grande envergure au sein de votre organisation, vous devez prendre en compte plusieurs facteurs avant de commencer à le configurer. 

## <a name="who-can-create-and-schedule-live-events"></a>Qui peut créer et planifier des événements en direct? 
Les conditions préalables suivantes sont requises pour l’utilisateur pour planifier un événement en direct Teams.

Les licences qui doivent être attribuées sont les suivantes:  
- Licence Office 365 entreprise E1, E3 ou E5, ou licence Office 365 a3 ou a5
- Licence Microsoft teams
- Licence Microsoft Stream

> [!IMPORTANT]
> L’utilisateur qui crée et planifie un événement en direct doit avoir une boîte aux lettres Exchange Online.

Il est important de savoir qu’une licence Office 365 est requise pour participer à un événement en direct en tant qu’utilisateur authentifié, mais cette obligation dépend de la méthode de production utilisée:

- **Pour les événements produits dans teams**  Une licence d’équipe doit être attribuée à l’utilisateur.
- **Pour les événements produits avec une application ou un appareil externe** Une licence de flux doit être attribuée à l’utilisateur.

Pour plus d’informations sur les licences, voir [licences de complément Microsoft teams](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

L’utilisateur doit avoir:
- Planification de réunions privées en équipes activées (*paramètre TeamsMeetingPolicy-AllowPrivateMeetingScheduling = true*).
- Partage vidéo activé dans les réunions Teams (*paramètre TeamsMeetingPolicy-AllowIPVideo = true*).
- Le partage d’écran est activé dans les réunions Teams (*paramètre TeamsMeetingPolicy-ScreenSharingMode = EntireScreen*).
- Planification d’événements en direct dans équipes activées (*paramètre TeamsMeetingBroadcastPolicy-AllowBroadcastScheduling = true*).
- Autorisations de création d’événements en direct dans le flux (pour la production d’applications ou de périphériques externes).

> [!IMPORTANT]
> Les utilisateurs d’Office 365, fédérés et anonymes ne peuvent pas être invités en tant que producteurs ou présentateurs dans des événements en direct Teams. Les utilisateurs d’Office 365 invités et fédérés peuvent uniquement surveiller les événements dynamiques de manière anonyme. 
 
## <a name="who-can-watch-live-events"></a>Qui peut regarder des événements en direct?

|**Visibilité des participants**       |**Production teams**  |**Production d’applications ou de périphériques externes**  |
|------------------------------|-----------------|----------------------|
|Public (utilisateurs anonymes)      |  Oui            |  Non                  |
|Utilisateurs invités                   |  No<sup>1</sup> |  Non                  |
|Tout le monde dans la société fédérée |  No<sup>1</sup> |  Non                  |
|Tout le monde dans la société           |  Oui             |  Oui                 |
|Groupes/personnes spécifiques      |  Oui             |  Oui                 |

<sup>1</sup> peut uniquement surveiller les événements en direct en tant qu’utilisateurs anonymes.

 
## <a name="teams-live-events-and-skype-meeting-broadcast"></a>Événements en direct teams et diffusion de réunion Skype
Le tableau suivant met en évidence les fonctionnalités principales et les fonctionnalités proposées dans les événements en direct et la façon dont ils diffèrent de la diffusion de réunion Skype. 

|**Faculté**   |**Diffusion de réunion Skype** |**Événements produits dans teams** |**Événements produits dans une application ou un appareil externes** |
|---------|---------|---------|---------|
|Taille maximale du public |participants 10 000 |10 000 participants * |10 000 participants * |
|Durée maximale de l’événement en direct |4 heures |4 heures |4 heures |
|Nombre maximal d’événements en direct simultanés par client Office 365 |0,15  | 0,15  | 0,15  |
|Création d’événements en direct |   Portail de diffusion de réunion Skype |Teams, Yammer via teams | Teams, Yammer par équipe, flux |
|Engagement public-Yammer |&#x2714; |&#x2714; (environnement intégré) |&#x2714; (environnement intégré) |
|Engagement d’audience: Q modéré Q & A |&#x2714;  |&#x2714; |&#x2714; |
|Client de Producer sur Windows |&#x2714; (Skype entreprise) |&#x2714; (Teams) |&#x2714; (flux, équipes via flux embed) |
|Client de Producer sur Mac |X  | &#x2714; (Teams) |&#x2714; (flux, équipes via flux embed) |
|Nombre de participants dans l’interface utilisateur de Producer |X  |&#x2714; (Teams) |&#x2714; (flux, équipes via flux embed) |
|Autorise plusieurs présentateurs |&#x2714; (Skype entreprise) |&#x2714; (Teams) |S/O  |
|Inviter un présentateur lors de la réunion |&#x2714; (Skype entreprise) |X |S/O |
|Participation du présentateur sur le Web et le mobile |&#x2714; (Skype entreprise)  |X |S/O |
|Personnes distantes de présentateurs & invités |&#x2714; (Skype entreprise)  | (bientôt disponible) |S/O |
|Présentateur-accès RTC |X |&#x2714; (Teams) |S/O |
|Présenter un écran |X |&#x2714; (Teams) |S/O |
|Présenter une présentation PowerPoint (de partage PPT) |&#x2714; |X (atténué via le partage d’écran) |S/O |
|Enregistrement d’une réunion basée sur le Cloud |&#x2714; |&#x2714; |&#x2714; |
|Publier automatiquement l’enregistrement dans le flux |X |X |&#x2714; |
|Légendes et traductions en temps réel |&#x2714; |&#x2714; (bientôt disponible) |X |
|Légendes dans les enregistrements d’événements en direct |&#x2714; |&#x2714; (bientôt disponible) |&#x2714; |
|Contrôles de participants DVR (pause, rembobinage) |&#x2714; |&#x2714; |&#x2714; |
|Support technique de eCDN partenaire |&#x2714; (Hive, Kollective, RAMP) |&#x2714; (Hive, Kollective, RAMP) |&#x2714; (Hive, Kollective, RAMP) |
|Rapport de présence après diffusion pour les producteurs |&#x2714; |&#x2714; |X |
|Analyse d’un sentiment d’audience: vote en direct & sondages |&#x2714; (Microsoft Pulse) |X |X |

> [!IMPORTANT]
> Les limites définies peuvent être modifiées.

## <a name="regional-availability"></a>Disponibilité régionale
Vous pouvez utiliser des événements en direct teams dans plusieurs régions dans le monde entier. Les informations suivantes indiquent la disponibilité pour les membres de l’équipe et les participants. 

> [!IMPORTANT]
> La région de l’événement est automatiquement sélectionnée en fonction de l’organisateur et de l’organisation Office 365.

**Disponible dans les régions suivantes**
- Amérique
- Europe/Afrique
- Asie-Pacifique
- Go local Canada

**Exclusions et considérations**
- Rendez-vous **locales:** Le Royaume-Uni, l’Inde, l’Australie, le Japon et d’autres équipes ne sont pas pris en charge pour le moment.
- **Chine:** Les membres de l’équipe et les participants ne seront pas en mesure d’utiliser les événements teams Live car Azure CDN n’est pas accessible en Chine. Pour contourner ce problème, vous pouvez utiliser une connexion VPN d’entreprise, qui obtient le client connecté au CDN via le réseau d’entreprise du client.

## <a name="next-steps"></a>Étapes suivantes
Accédez à [configurer pour les événements en direct teams](set-up-for-teams-live-events.md).

### <a name="related-topics"></a>Voir aussi
- [Que sont les événements en direct Teams ?](what-are-teams-live-events.md)
- [Configurer les événements en direct Teams](set-up-for-teams-live-events.md)
- [Configurer les paramètres des événements en direct dans teams](configure-teams-live-events.md)

