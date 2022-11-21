---
title: Présentation des événements en direct Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.collection:
- M365-collaboration
- m365initiative-meetings
- m365solution-spcomms
- m365solution-scenario
- highpri
ms.reviewer: sonua
audience: admin
search.appverid: MET150
description: Découvrez comment les événements en direct permettent aux utilisateurs de diffuser des vidéos et du contenu à une large audience d’internautes dans Teams, Yammer et Stream.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.liveevents
- ms.teamsadmincenter.liveevents.policies
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: fb6e808b162736b5d3e682cf8ae00682b4334388
ms.sourcegitcommit: baf29d244b428712052553f9e4484e72e727247e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2022
ms.locfileid: "69046753"
---
# <a name="what-are-microsoft-teams-live-events"></a>Présentation des événements en direct Microsoft Teams

## <a name="overview"></a>Vue d’ensemble

Grâce aux événements en direct Teams, les utilisateurs de votre organisation peuvent diffuser du contenu vidéo et des réunions à une large audience d’internautes.

Les événements en direct de Microsoft 365 améliorent considérablement la diffusion vidéo en direct. Les événements en direct favorisent les liens tout au long du cycle de vie de l’engagement avec les participants, et ce, avant, pendant et après les événements en direct. Vous pouvez créer un événement en direct peu importe où se trouvent votre audience, votre équipe ou votre communauté, à l’aide de Microsoft Stream, Teams ou Yammer.  

Teams propose une collaboration, des appels, des réunions et des événements en direct basés sur la conversation, afin que vous puissiez élargir l’audience de vos réunions. Les événements en direct Teams sont une extension des réunions Teams, permettant aux utilisateurs de diffuser des vidéos et du contenu de réunion à une large audience d’internautes. Les événements en direct sont destinés aux communications un-à-plusieurs dans lesquelles l’hôte de l’événement dirige les interactions. La participation de l’audience se résume principalement à afficher le contenu partagé par l’hôte. Les participants peuvent regarder l’événement en direct ou enregistré dans Yammer, Teams ou Stream et peuvent interagir avec les présentateurs à l’aide des questions et réponses modérées ou d’une conversation Yammer.

Les événements en direct des équipes sont considérés comme la prochaine version de la Diffusion de réunion Skype et remplaceront à terme les fonctionnalités fournies dans celle-ci. À ce stade, Microsoft continuera à prendre en charge la Diffusion de réunion Skype pour les utilisateurs qui utilisent Skype Entreprise dans leurs organisations, sans interruption de service pour les événements nouveaux ou futurs. Cependant, nous vous encourageons à essayer les événements en direct Teams pour utiliser toutes les nouvelles fonctionnalités intéressantes, notamment le partage d’écran et la prise en charge des encodeurs matériels/logiciels externes.

So, let's get started. First, take a look at the following diagram that shows high level components involved in Microsoft 365 live events and how they're connected.

![Les éléments clés des événements en direct.](../media/live-events-flow-diagram.png  "Composants clés des événements en direct, planification, production, plateforme Stream, fournisseurs tiers certifiés eCDN")

> [!Note]
> Nous aimerions souligner que les événements en direct Teams, étant donné la nature de la technologie de diffusion, dépassent souvent les populations de réunions normales (internes).
>
> Comme c’est le cas avec d’autres services de diffusion multimédia de plus grande envergure, nous nous appuyons sur les réseaux de distribution de contenu pour remettre le contenu de votre événement en direct aux destinataires. Ce contenu est protégé par des méthodes de chiffrement et soumis à autorisation par des jetons d’accès qui sont émis uniquement aux destinataires en fonction de la configuration de votre réunion d’événement en direct.
>
> Il convient de veiller tout particulièrement à ce que le contenu de la réunion soit adapté à un public aussi important, ou à ce que le public soit réduit de manière appropriée en cas de contenu sensible.  
>
> Comme c’est courant dans le secteur, les compromissions avec d’autres éléments de votre sécurité, tels que le personnel ou l’infrastructure, peuvent avoir un impact sur la sécurité de vos événements en direct. Les organisations doivent envisager d’inclure les événements en direct et d’autres services de diffusion dans leurs exercices et planification de la sécurité.

### <a name="event-group-roles"></a>Rôles du groupe d’événements

Les événements en direct dans Teams permettent à plusieurs rôles (organisateur, producteur, présentateur et participant) de diffuser et de participer avec succès à un événement. Si vous souhaitez en savoir plus, consultez l’article [Rôles du groupe d’événements](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a?ui=en-US&rs=en-US&ad=US#bkmk_roles).

## <a name="key-components"></a>Composants clés

Vous pouvez voir sur l’image ci-dessus que cinq composants clés sont utilisés avec les événements en direct dans Teams.

> [!NOTE]
> Si vous souhaitez consulter une présentation de la configuration des événements en direct et de l’expérience des participants, regardez ces courtes [vidéos](https://support.office.com/article/video-plan-and-schedule-a-live-event-f92363a0-6d98-46d2-bdd9-f2248075e502).

### <a name="scheduling"></a>Planification

Teams permet aux organisateurs de créer un événement avec les autorisations de participant appropriées, de désigner les membres de l’équipe de l’événement, de sélectionner une méthode de production et d’inviter des participants. Si l’événement en direct a été créé à partir d’un groupe Yammer, les participants à l’événement peuvent utiliser la conversation Yammer pour interagir.

![L’écran Nouveaux événements en direct.](../media/teams-live-events-schedule.png "Capture d’écran montrant l’écran Nouvel événement en direct pour créer et programmer un nouvel événement en direct")

> [!IMPORTANT]
> Teams ne permet pas aux utilisateurs de planifier de réunions ou d’événements en direct lorsqu’ils sont hors connexion ou qu’ils utilisent une bande passante limitée.

### <a name="production"></a>Production

L’entrée vidéo est la base de l’événement en direct et vous pouvez utiliser une seule webcam mais aussi une production vidéo professionnelle multi-caméras. Les événements en direct dans Microsoft 365 prennent en charge un éventail de scénarios de production, incluent un événement produit dans Teams à l’aide d’une webcam ou un événement produit dans une application ou un appareil externe. Vous pouvez choisir ces options en fonction des exigences du projet et du budget. Il existe deux façons de produire des événements :

- **Teams** : Cette méthode de production permet aux utilisateurs de produire leurs événements en direct dans Teams en utilisant leur webcam ou en utilisant l’entrée A/V des systèmes de salle Teams. Cette option est la meilleure et la plus rapide si vous souhaitez utiliser les périphériques audio et vidéo connectés au PC ou si vous invitez des présentateurs distants à participer à l’événement. Cette option permet aux utilisateurs d’utiliser facilement leurs webcams et de partager leur écran en tant qu’entrée dans l’événement.

- **Application ou appareil externe** : Les encodeurs externes permettent aux utilisateurs de produire leurs événements en direct directement à partir d’un encodeur matériel ou logiciel externe avec [Stream](https://stream.microsoft.com). Cette option est préférable si vous disposez déjà d’un équipement de qualité studio (par exemple, des logiciels de mixage multimédias) qui prennent en charge la diffusion en continu vers un service RTMP (Real-time Messaging Protocol). Ce type de production est généralement utilisé dans les événements à grande échelle tels que les mairies, dans lesquelles un seul flux du logiciel de mixage multimédia est diffusé au public.

    ![Un événement en direct produit à l’aide d’une application ou d’un appareil externe.](../media/teams-live-events-external-encoder.png "Capture d’écran montrant un événement en direct produit à l’aide de l’application externe ou de la méthode de production de l’appareil")

>[!Note]
> The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](../tmr-meeting-recording-change.md) will be a phased approach. At launch you'll be able to opt-in to this experience, in November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.

### <a name="streaming-platform"></a>Plateforme de diffusion en continu

La plateforme de diffusion en continu d’événements en direct est composée des éléments suivants :

- **Azure Media Services** :  [Azure Media Services](/azure/media-services/previous/) vous offre des services de diffusion vidéo en continu pour atteindre un public plus large sur les appareils mobiles les plus populaires du moment. Media Services améliore l’accessibilité, la distribution et l’évolutivité, et permettent de diffuser facilement et à faible coût du contenu auprès de votre public local ou international, tout en protégeant votre contenu.
- **Azure Content Delivery Network (CDN)** :  Une fois votre flux mis en ligne, il est diffusé via [Azure Content Delivery Network (CDN)](/azure/cdn/). Azure Media Services fournit un CDN intégré pour les points de terminaison de diffusion en continu. Cela permet aux flux d’être visualisés dans le monde entier sans mise en mémoire tampon.

### <a name="enterprise-content-delivery-network-ecdn"></a>Réseau de diffusion de contenu d’entreprise (eCDN)

L’objectif du eCDN est de récupérer le contenu vidéo à partir d’Internet et de le diffuser dans toute votre entreprise sans affecter les performances du réseau. Vous pouvez utiliser la [solution eCDN interne de Microsoft](/ecdn) ou, sinon, l’un des partenaires eCDN certifiés suivants pour optimiser votre réseau pour les événements en direct organisés au sein de votre organisation :

- [Hive](https://www.hivestreaming.com/partners/integration-partners/microsoft/)
- [Kollective](https://kollective.com/ecdn-solutions/microsoft-live-events/)
- [Ramp](https://rampecdn.com)
- [Riverbed](https://www.riverbed.com/solutions/office-365.html)

### <a name="attendee-experience"></a>Expérience des participants

L’expérience des participants est l’aspect le plus important des événements en direct et il est essentiel que les participants puissent participer à l’événement en direct sans aucun problème. L’expérience des participants utilise le lecteur Stream (pour les événements produits dans Teams) et le Lecteur multimédia Azure (pour les événements produits dans une application ou un appareil externe) et fonctionne sur bureau, navigateur et mobile (iOS, Android). Microsoft 365 et Office 365 fournissent Yammer et Teams, deux hubs de collaboration, et l’expérience des participants en direct est intégrée à ces outils de collaboration.

![Exemple d’expérience des participants aux événements en direct.](../media/teams-live-events-attendee.png "Capture d’écran montrant l’expérience des participants aux événements en direct")

### <a name="live-event-usage-report"></a>Rapport d’utilisation des événements en direct

Les administrateurs de client peuvent afficher des analyses d’utilisation en temps réel pour les événements en direct dans le centre d’administration Microsoft Teams.  Le [rapport d’utilisation des événements en direct](../teams-analytics-and-reports/teams-live-event-usage-report.md) affiche une vue d’ensemble des activités des événements en direct organisés dans l’organisation.  Les administrateurs peuvent afficher les informations d’utilisation des événements, y compris l’état de l’événement, l’heure de début, les vues et le type de production.  

## <a name="next-steps"></a>Étapes suivantes

Accédez à[Planifier des événements en direct dans Microsoft Teams](plan-for-teams-live-events.md).

### <a name="related-topics"></a>Voir aussi

- [Événements en direct dans Microsoft 365 dans Yammer, Microsoft Teams et Microsoft Stream](/stream/live-event-m365)
- [Prise en main des événements en direct Microsoft Teams](https://support.office.com/article/d077fec2-a058-483e-9ab5-1494afda578a)
- [Événements en direct dans Yammer](https://support.office.com/article/live-events-in-yammer-4ece0ee2-c268-4636-bf2a-16e454befe57)
- [Événements en direct dans Microsoft Stream](/stream/live-event-overview)
