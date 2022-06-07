---
title: Planifier des événements en direct dans Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: sonua
f1.keywords:
- NOCSH
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365initiative-meetings
- m365initiative-meetings-enabler
- enabler-strategic
search.appverid: MET150
description: Dans cet article, vous allez découvrir les facteurs à prendre en compte avant de configurer des événements en direct dans Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b39be09266f5af76064f867e721fab5146a75adc
ms.sourcegitcommit: 1ac37cc27d4ccb3e1dae20ca1929214e17be2075
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/07/2022
ms.locfileid: "65913442"
---
# <a name="plan-for-live-events-in-microsoft-teams"></a>Planifier des événements en direct dans Microsoft Teams

Lorsque vous planifiez des événements en direct Teams pour organiser des réunions de grande envergure au sein de votre organisation, vous devez tenir compte de plusieurs facteurs avant de démarrer la configuration.

> [!Note]
> Pour plus d’informations sur les événements en direct Teams sur différentes plateformes, consultez [Fonctionnalités Teams par plateforme](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3). Pour en savoir plus sur les exigences en matière de bande passante pour les événements en direct Teams [préparer votre organisation](../prepare-network.md).

## <a name="who-can-attend-create-and-schedule-live-events"></a>Qui peut rejoindre, créer et planifier des événements en direct ?

Tout le monde, avec ou sans licence, peut participer à un événement en direct. Lisez  [Démarrage rapide : réunions et événements en direct](../quick-start-meetings-live-events.md).

Les conditions suivantes sont requises pour un utilisateur pour configurer un événement en direct Teams.

Voici les licences à attribuer pour organiser, produire ou présenter un événement en direct Teams :  

- **Pour organiser :** licence Microsoft ou Office 365 Entreprise E1, E3 ou E5, **[ou]** licence Microsoft ou Office 365 Éducation A3 ou A5. 
- **Pour produire ou présenter :** une licence Microsoft ou Office 365 Entreprise E1, E3 ou E5, **[ou]** une licence Microsoft ou Office 365 Éducation A1, A3 ou A5. L’exception à cette exigence est que les utilisateurs invités peuvent se présenter sans licence si les autres critères pour [utilisateurs invités](plan-for-teams-live-events.md#guest-to-present) sont satisfaits.
- Licence Microsoft Teams : cette licence fait partie des licences répertoriées dans les première et seconde puces.
- Une licence Microsoft Stream est nécessaire si vous envisagez de partager du contenu sur une application ou un service externe. Voir [Licence Microsoft Stream](/stream/license-overview).

  Les utilisateurs n’ont pas besoin de licence Microsoft Stream affecté si vous voulez que les utilisateurs enregistrent et téléchargent uniquement les enregistrements. Cela signifie que les enregistrements ne sont pas stockés dans Microsoft Stream, mais stockés dans Azure Media Services (AMS) avec une limite de 180 jours avant sa suppression. À ce stade, un administrateur peut contrôler ou gérer pour inclure la possibilité de le supprimer.

>[!Note]
> Les modifications apportées à l’utilisation de Microsoft Stream pour [OneDrive Entreprise et SharePoint pour les enregistrements de réunion](../tmr-meeting-recording-change.md) auront une approche progressive.Au moment du lancement, vous pourrez choisir de participer à cette expérience. En novembre, vous devrez vous désengager si vous souhaitez continuer à utiliser Stream et début 2021, nous demanderons à tous les clients d'utiliser OneDrive Entreprise et SharePoint pour les nouveaux enregistrements de réunions.

> [!NOTE]
> Pour l’instant, il n’existe aucune offre Microsoft 365 pour les petites entreprises pouvant être utilisée pour créer et organiser des événements Teams en direct.

Il est important de comprendre qu’une licence Microsoft 365 ou Office 365 est requise pour participer à un événement en direct en tant qu’utilisateur authentifié, mais cette exigence dépend de la méthode de production utilisée :

- **Pour les événements produits dans Teams**, l’utilisateur doit disposer d’une licence Teams.
- **Pour les événements produits à l’aide d’un appareil ou d’une application externe**, l’utilisateur doit disposer d’une licence Stream.

> [!NOTE]
> Les événements live Teams sont désormais disponibles pour les organisations de la communauté Cloud du gouvernement américain (GCC).

Pour plus d’informations sur les licences, voir [Licences de module complémentaire Microsoft Teams](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

L’utilisateur doit disposer des éléments suivants :

- Planification des réunions privées dans Teams activée (*paramètre TeamsMeetingPolicy-AllowPrivateMeetingScheduling = True*).
- Partage de vidéos activé pour les réunions Teams (*paramètre TeamsMeetingPolicy-AllowIPVideo = True*).
- Partage d’écran activé pour les réunions Teams (*paramètre TeamsMeetingPolicy--ScreenSharingMode = EntireScreen*).
- Planification des événements en direct dans Teams activée (*paramètre TeamsMeetingPolicy-AllowBroadcastScheduling = True*).
- Autorisations pour créer des événements live dans Stream (pour production sur une application ou appareil externe).
- Le mode de coexistence est configuré pour planifier les réunions Teams(*îles, réunions en premier, ou Teams uniquement*).

> [!IMPORTANT]
> Les utilisateurs anonymes non authentifiés ne peuvent pas être invités en tant que producteurs ou présentateurs dans les événements Teams en direct.

### <a name="guest-to-present"></a>[Invité à présenter](#guest-to-present)

Pour qu'un invité fasse une présentation dans un événement en direct, procédez comme suit :

1. [Ajoutez l’utilisateur en tant qu’invité à une équipe](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).
2. Demandez à l’utilisateur d’accepter l’invitation invité et de rejoindre l’équipe.
3. [Planifiez l’événement en direct et ajoutez l’invité à votre groupe d’événements](https://support.microsoft.com/article/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2).

Nous vous recommandons de créer un canal pour les fabricants et présentateurs de l’événement en direct, afin qu’ils puissent discuter et partager des informations avant l’événement. Les invités qui n’ont pas d’informations d’identification Microsoft 365 ne pourront pas afficher le calendrier dans Teams. Pour permettre aux utilisateurs de participer aisément à l’événement, les producteurs peuvent publier le lien de l’événement vers le canal. Les présentateurs peuvent ensuite ouvrir Teams, accéder au canal, puis sélectionner le lien pour participer à l’événement.

## <a name="who-can-watch-live-events"></a>Qui peut regarder les événements en direct

| Visibilité des participants | Production Teams | Production appareil ou application externe |
|------------------------------|-----------------|----------------------|
|Public (utilisateurs anonymes)      |  Oui            |  Non                  |
|Utilisateurs invités                   |  Oui <sup>1</sup>            |  Non                  |
|Tout membre d’une entreprise ayant un accès externe (fédération)  |  Oui <sup>1</sup>|  Non                  |
|Tous les membres de l’entreprise           |  Oui            |  Oui                 |
|Des groupes / personnes spécifiques      |  Oui            |  Oui                 |

<sup>1</sup> peuvent uniquement être invités via des contacts et groupe <br>

## <a name="teams-live-events-and-skype-meeting-broadcast"></a>Événements en direct Teams et Diffusion de réunion Skype

Le tableau suivant souligne les capacités et fonctionnalités essentielles proposées dans les événements en direct et la manière dont elle diffèrent de la Diffusion de réunion Skype.

> [!IMPORTANT]
> **Augmentation de la limite d’événements en direct Microsoft 365**
>
> **Pour continuer à répondre aux besoins de nos clients, nous prolongerons les augmentations de limites temporaires pour les événements en direct jusqu'au 31 décembre 2022, notamment**:
>
>- Soutien aux événements accueillant jusqu'à 20 000 participants
>- 50 événements à la fois peuvent être hébergés chez un client
>- Durée de l'événement : 16 heures par diffusion
>
> En plus les évènements en direct avec plus de 100 000 participants peuvent être planifiés à travers le programme d’assistance événements en direct Microsoft 365. L’équipe évaluera chaque demande et travail avec vous pour déterminer les options disponibles. [En savoir plus](https://aka.ms/Stream/Blog/LiveEventOptions). 

| Fonctionnalité | Diffusion de réunion Skype | Événements générés dans Teams | Événements générés dans une application ou un appareil externe |
|---------|---------|---------|---------|
|Taille maximale du public |10 000 participants |10 000 participants<sup>1</sup> |10 000 participants<sup>1</sup> |
|Durée maximale de l’événement en direct |4 heures |4 heures |4 heures |
|Nombre maximal de présentateurs et de producteurs en temps réel |10 <sup>2</sup> |10 <sup>2</sup> |10 <sup>2</sup> |
|Nombre maximal d’événements en direct simultanés par Microsoft 365 ou l’organisation Office 365 |15  | 15  | 15  |
|Création d’événement en direct |   Portail de diffusion de réunion Skype |Teams, Yammer via Teams | Teams, Yammer via Teams, Stream |
|Engagement d’audience - Yammer |&#x2714; |&#x2714; (expérience intégrée) |&#x2714; (expérience intégrée) |
|Engagement d’audience - Q&R modérées |&#x2714;  |&#x2714; |&#x2714; |
|Client Producteur sur Windows |&#x2714; (Skype Entreprise) |&#x2714; (Teams) |&#x2714; (Stream, Teams via Stream Embed) |
|Client Producteur sur Mac |&#x274C;  | &#x2714; (Teams) |&#x2714; (Stream, Teams via Stream Embed) |
|Nombre de participants dans l’interface utilisateur producteur |&#x274C;  |&#x2714; (Teams) |&#x2714; (Stream, Teams via Stream Embed) |
|Autorise plusieurs présentateurs |&#x2714; (Skype Entreprise) |&#x2714; (Teams) |N/A  |
|Inviter un présentateur pendant la réunion |&#x2714; (Skype Entreprise) |&#x274C; |S/O |
|Présentateur participe sur le Web et Mobile |&#x2714; (Skype Entreprise)  |&#x274C; |S/O |
|Accès externe (fédération) et présentateurs/participants invités |&#x2714; (Skype Entreprise)  |  &#x2714; (Teams) |S/O |
|Présentateur - accès PSTN |&#x274C; |&#x2714; (Teams) |N/A |
|Présenter un écran |&#x274C; |&#x2714; (Teams) |S/O |
|Partage du système audio sous Windows (disponible uniquement lors du partage d’écran)|&#x274C; |&#x2714; (Teams) |&#x2714; |
|Présenter un PowerPoint (partage PPT) |&#x2714; |&#x274C; (atténué via le partage d’écran) |S/O |
|Enregistrement de réunion sur le Cloud |&#x2714; |&#x2714; |&#x2714; |
|Publier automatiquement l’enregistrement sur Stream |&#x274C; |&#x274C; |&#x2714; |
|Légendes et sous-titres en direct |&#x2714; |&#x2714; |&#x274C; |
|Légendes dans les enregistrements d’événements en direct |&#x2714; |&#x2714; |&#x2714; |
|Contrôles DVR de participants (pause, rembobinage) |&#x2714; |&#x2714; |&#x2714; |
|Support eCDN partenaire |&#x2714; (Kollective, Hive) |&#x2714; (Kollective, Hive, Ramp, Riverbed) |&#x2714; (Hive, Kollective, Ramp, Riverbed) |
|Rapport de présence après diffusion pour les producteurs |&#x2714; |&#x2714; |&#x274C; |
|Analyse de l’audience : vote en direct & sondages |&#x2714; (Microsoft Pulse) |&#x274C; |&#x274C; |

<sup>1</sup> Les limites définies peuvent être modifiées. Consultez [Spécifications et limites de Microsoft Teams](../limits-specifications-teams.md).<br/>
<sup>2</sup> vous pouvez avoir jusqu’à 100 présentateurs et producteurs dans un événement en direct, mais seules les 10 dernières qui en ont fait mention dans la liste.

## <a name="regional-availability"></a>Disponibilité régionale

Vous pouvez utiliser les événements en direct Teams dans plusieurs régions dans le monde entier. Les informations suivantes montrent la disponibilité pour les membres de l’équipe et des participants de l’événement.

> [!IMPORTANT]
> La région de l’événement est sélectionnée automatiquement en fonction de l’organisateur et de l’emplacement du locataire Microsoft 365.

**Disponible dans ces centres de données régionaux**

- Amérique du Nord
- Amérique Centrale
- Amérique du Sud
- Asie-Pacifique
- Europe/Afrique

**Emplacement des données pour ces pays/régions (pris en charge)**

- Australie
- Brésil
- Canada
- France
- Allemagne
- Inde
- Japon
- Norvège
- Singapour
- Afrique du Sud
- Corée du Sud
- Suisse
- UAE
- Royaume-Uni

**Exclusions et points à prendre en compte**

- **Emplacement des données :** les emplacements de données de Teams, en dehors de ceux répertoriés ci-dessus, ne sont pas pris en charge pour le moment.

## <a name="next-steps"></a>Étapes suivantes

Accédez à[Configurer les événements en direct Teams](set-up-for-teams-live-events.md).

### <a name="related-topics"></a>Sujets associés

- [Comprendre un événement en direct Teams](what-are-teams-live-events.md)
- [Configurer les événements en direct Teams](set-up-for-teams-live-events.md)
- [Configurer les paramètres d’événements en direct dans Teams](configure-teams-live-events.md)
