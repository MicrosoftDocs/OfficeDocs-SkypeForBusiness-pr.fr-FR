---
title: Planifier des événements en direct dans Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 08/19/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: sonua
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Découvrez les facteurs à prendre en compte avant de configurer des événements live dans Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2f70a7a2be51045f616ebb4cedc5baf46dbe101d
ms.sourcegitcommit: 56ceda54ca48d2984298d4d1f26017c0147d4431
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/14/2020
ms.locfileid: "43505621"
---
# <a name="plan-for-live-events-in-microsoft-teams"></a>Planifier des événements en direct dans Microsoft Teams

Lorsque vous planifiez des événements en direct Teams pour organiser des réunions de grande envergure au sein de votre organisation, vous devez tenir compte de plusieurs facteurs avant de commencer à les configurer. 

## <a name="who-can-create-and-schedule-live-events"></a>Qui peut créer et planifier des événements en direct ? 
Les conditions suivantes sont requises pour un utilisateur pour configurer un événement en direct Teams.

Voici les licences qui doivent être attribuées :  
- Une licence Office 365 Entreprise E1, E3 ou E5, ou une licence Office 365 A3 ou A5
- Une licence Microsoft Teams
- Une licence Microsoft Stream

> [!IMPORTANT]
> L’utilisateur créant et planifiant un événement en direct doit avoir une boîte aux lettres Exchange Online.

Il est important de comprendre qu’une licence Office 365 est requise pour participer à un événement en direct en tant qu’utilisateur authentifié, mais cette exigence dépend de la méthode de production utilisée :

- **Pour les événements produits dans Teams**, l’utilisateur doit disposer d’une licence Teams.
- **Pour les événements produits à l’aide d’un appareil ou d’une application externe**, l’utilisateur doit disposer d’une licence Stream.

> [!NOTE]
> Les événements live Teams sont désormais disponibles pour les organisations de la communauté Cloud du gouvernement américain (GCC).

Pour plus d’informations sur les licences, voir [Licences de module complémentaire Microsoft Teams](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

L’utilisateur doit disposer des éléments suivants :
- Planification des réunions privées dans Teams activée (*paramètre TeamsMeetingPolicy-AllowPrivateMeetingScheduling = True*).
- Partage de vidéos activé pour les réunions Teams (*paramètre TeamsMeetingPolicy-AllowIPVideo = True*).
- Partage d’écran activé pour les réunions Teams (*paramètre TeamsMeetingPolicy--ScreenSharingMode = EntireScreen*).
- Planification des événements en direct dans Teams activée (*paramètre TeamsMeetingPolicy-AllowBroadcastScheduling = True*).
- Autorisations pour créer des événements live dans Stream (pour production sur une application ou appareil externe).
- Le mode de coexistence configuré pour être en mesure de planifier des réunions d’équipes (*îlots, réunions, premier ou équipes uniquement*).

> [!IMPORTANT]
> Les utilisateurs anonymes non authentifiés ne peuvent pas être invités en tant que producteurs ou présentateurs dans les événements live Teams. 
 
## <a name="who-can-watch-live-events"></a>Qui peut consulter les événements en direct ?

|**Visibilité des participants**       |**Production Teams**  |**Production appareil ou application externe**  |
|------------------------------|-----------------|----------------------|
|Public (utilisateurs anonymes)      |  Oui            |  Non                  |
|Utilisateurs invités                   |  Oui            |  Non                  |
|Tous les membres de l’entreprise fédérée |  Oui<sup>1</sup>|  Non                  |
|Tous les membres de l’entreprise           |  Oui            |  Oui                 |
|Des groupes / personnes spécifiques      |  Oui            |  Oui                 |

<sup>1</sup> les participants fédérés peuvent uniquement être invités par le biais de personnes & groupe <br>
 
## <a name="teams-live-events-and-skype-meeting-broadcast"></a>Événements en direct Teams et Diffusion de réunion Skype

Le tableau suivant souligne les capacités et fonctionnalités essentielles proposées dans les événements en direct et la manière dont elle diffèrent de la Diffusion de réunion Skype. 

|**Fonctionnalité**   |**Diffusion de réunion Skype** |**Événements générés dans Teams** |**Événements générés dans une application ou un appareil externe** |
|---------|---------|---------|---------|
|Taille maximale de l’audience |10 000 participants |10 000 participants<sup>1</sup> |10 000 participants<sup>1</sup> |
|Durée maximale de l’événement en direct |4 heures |4 heures |4 heures |
|Nombre maximal de présentateurs et de producteurs dans un événement en direct |10 <sup>2</sup> |10 <sup>2</sup> |10 <sup>2</sup> |
|Nombre maximal d’événements en direct simultanés par client Office 365 |0,15  | 0,15  | 0,15  |
|Création d’événement en direct |   Portail de diffusion de réunion Skype |Teams, Yammer via Teams | Teams, Yammer via Teams, Stream |
|Engagement d’audience - Yammer |&#x2714; |&#x2714; (expérience intégrée) |&#x2714; (expérience intégrée) |
|Engagement d’audience - Q&R modérées |&#x2714;  |&#x2714; |&#x2714; |
|Client Producteur sur Windows |&#x2714; (Skype Entreprise) |&#x2714; (Teams) |&#x2714; (Stream, Teams via Stream Embed) |
|Client Producteur sur Mac |&#x274C;  | &#x2714; (Teams) |&#x2714; (Stream, Teams via Stream Embed) |
|Nombre de participants dans l’interface utilisateur producteur |&#x274C;  |&#x2714; (Teams) |&#x2714; (Stream, Teams via Stream Embed) |
|Autorise plusieurs présentateurs |&#x2714; (Skype Entreprise) |&#x2714; (Teams) |S/O  |
|Inviter un présentateur pendant la réunion |&#x2714; (Skype Entreprise) |&#x274C; |S/O |
|Présentateur participe sur le Web et Mobile |&#x2714; (Skype Entreprise)  |&#x274C; |S/O |
|Présentateurs / Participants fédérés & invités |&#x2714; (Skype Entreprise)  |  &#x2714; (Teams) |S/O |
|Présentateur - accès PSTN |&#x274C; |&#x2714; (Teams) |S/O |
|Présenter un écran |&#x274C; |&#x2714; (Teams) |S/O |
|Présenter un PowerPoint (partage PPT) |&#x2714; |&#x274C; (atténué via le partage d’écran) |S/O |
|Enregistrement de réunion sur le Cloud |&#x2714; |&#x2714; |&#x2714; |
|Publier automatiquement l’enregistrement sur Stream |&#x274C; |&#x274C; |&#x2714; |
|Légendes et sous-titres en direct |&#x2714; |&#x2714; |&#x274C; |
|Légendes dans les enregistrements d’événements en direct |&#x2714; |&#x2714; |&#x2714; |
|Contrôles DVR de participants (pause, rembobinage) |&#x2714; |&#x2714; |&#x2714; |
|Support eCDN partenaire |&#x2714; (Hive, Kollective, Ramp) |&#x2714; (Hive, Kollective, Ramp) |&#x2714; (Hive, Kollective, Ramp) |
|Rapport de présence après diffusion pour les producteurs |&#x2714; |&#x2714; |&#x274C; |
|Analyse de l’audience : vote en direct & sondages |&#x2714; (Microsoft Pulse) |&#x274C; |&#x274C; |

<sup>1</sup> Les limites définies peuvent être modifiées. Vérifier les [limites et les spécifications pour teams](../limits-specifications-teams.md).<br/>
<sup>2</sup> vous pouvez avoir jusqu’à 250 de présentateurs et producteurs dans un événement en direct, mais uniquement les 10 derniers qui s’affichent dans la liste.


## <a name="regional-availability"></a>Disponibilité régionale
Vous pouvez utiliser les événements en direct Teams dans plusieurs régions dans le monde entier. Les informations suivantes montrent la disponibilité pour les membres de l’équipe et des participants de l’événement. 

> [!IMPORTANT]
> La région de l’événement est sélectionnée automatiquement en fonction de l’organisateur et de l’organisation Office 365.

**Disponible dans ces régions**
- Amériques
- Europe/Afrique
- Asie-Pacifique
- Go local au Canada, Inde, Australie, Japon, Royaume-Uni

**Exclusions et points à prendre en compte**
- **Go Locals:** Teams Go Locals, en dehors de celles répertoriées ci-dessus, ne sont pas prises en charge pour le moment.
- **Chine :** membres de l’équipe et les participants ne pourront pas utiliser les événements en direct Teams parce qu’Azure CDN n’est pas accessible en Chine. Une solution de contournement consiste à utiliser une connexion VPN d’entreprise qui permet au client de se connecter au réseau de distribution de contenu via le réseau d’entreprise du client.

## <a name="next-steps"></a>Étapes suivantes
Accédez à[Configurer les événements en direct Teams](set-up-for-teams-live-events.md).

### <a name="related-topics"></a>Sujets associés
- [Que sont les événements en direct Teams ?](what-are-teams-live-events.md)
- [Configurer les événements en direct Teams](set-up-for-teams-live-events.md)
- [Configurer les paramètres d’événements en direct dans Teams](configure-teams-live-events.md)
