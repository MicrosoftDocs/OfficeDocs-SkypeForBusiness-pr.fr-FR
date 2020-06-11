---
title: Que sont les événements en direct Microsoft Teams ?
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: sonua
audience: admin
search.appverid: MET150
description: Découvrez comment les événements dynamiques permettent aux utilisateurs de diffuser de la vidéo et du contenu sur des audiences en ligne de grande taille dans Teams, Yammer et en flux.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.liveevents
- ms.teamsadmincenter.liveevents.policies
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1ab528740947fa7efdd0608cec309757c3bb5eb2
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44689720"
---
# <a name="what-are-microsoft-teams-live-events"></a>Que sont les événements en direct Microsoft Teams ?

## <a name="overview"></a>Vue d’ensemble

Avec les événements en direct Teams, les utilisateurs de votre organisation peuvent diffuser du contenu vidéo et de réunion à des audiences en ligne de grande envergure. 

Dans le cadre de la diffusion en continu de vidéos en temps réel, vous pouvez créer des événements de connexion tout au long du cycle de vie de l’engagement avant, pendant et après les événements en direct. 365 Vous pouvez créer un événement en temps réel à l’endroit où votre public, équipe ou communauté réside, à l’aide de Microsoft Stream, d’équipes ou de Yammer.  

Teams permet la collaboration, les appels, les réunions et les événements en direct basés sur une conversation, afin que vous puissiez développer le public de vos réunions. Les événements en direct teams sont une extension des réunions Teams, ce qui permet aux utilisateurs de diffuser de la vidéo et du contenu de la réunion à un large public. Celles-ci sont destinées aux communications un-à-plusieurs à l’origine de l’hébergement d’interactions et de la participation de l’auditoire pour afficher le contenu partagé par l’hôte. Les participants peuvent voir l’événement en direct ou enregistré dans Yammer, teams et/ou Stream, et ils peuvent interagir avec les présentateurs à l’aide de la fonction Q modérée Q & A ou d’une conversation Yammer.

Les événements en direct teams sont considérés comme la prochaine version de la diffusion de réunion Skype et remplaceront les fonctionnalités fournies dans la diffusion de réunion Skype. À ce stade, Microsoft continuera à prendre en charge la diffusion de réunion Skype pour les utilisateurs de Skype entreprise dans leurs organisations, sans interruption de service pour les événements nouveaux ou futurs. Néanmoins, nous vous encourageons à essayer des événements en direct teams pour tirer parti de toutes les nouvelles fonctionnalités, notamment le partage d’écran et la prise en charge des encodeurs de matériel/logiciel externes.

Commençons. Tout d’abord, jetez un coup d’œil au schéma suivant montrant les composants de niveau supérieur impliqués dans les événements Microsoft 365 Live et la manière dont ils sont connectés. 

![Diagramme montrant les principaux composants des événements en direct](../media/teams-live-events.png  "Diagramme montrant les principaux composants des événements en direct, de planification, de production, de plate-forme de flux et de fournisseurs de services de eCDN tiers")

### <a name="event-group-roles"></a>Rôles des groupes d’événements
Les événements en direct dans teams permettent à plusieurs rôles (organisateur, producteur, présentateur et participant) de diffuser et de participer à un événement avec succès. Pour en savoir plus, voir [rôles des groupes d’événements](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a?ui=en-US&rs=en-US&ad=US#bkmk_roles).

## <a name="key-components"></a>Composants clés
Vous pouvez voir dans l’image ci-dessus qu’il existe quatre principaux composants utilisés avec des événements en direct dans Teams.

> [!NOTE]
> Pour obtenir une vue d’ensemble de la configuration des événements en direct et de l’utilisation des participants, regardez les courtes [vidéos](https://support.office.com/article/video-plan-and-schedule-a-live-event-f92363a0-6d98-46d2-bdd9-f2248075e502)suivantes.

### <a name="scheduling"></a>Tâches
Teams permet aux organisateurs de créer un événement avec les autorisations des participants appropriés, de désigner les membres de l’équipe d’événement, de sélectionner une méthode de production et d’inviter des participants. Si l’événement en direct a été créé à partir d’un groupe Yammer, les participants à l’événement en direct pourront utiliser la conversation Yammer pour interagir avec des personnes dans l’événement. 

![Capture d’écran montrant l’écran des nouveaux événements en direct](../media/teams-live-events-schedule.png "Capture d’écran montrant l’écran nouvel événement en direct pour créer et planifier un événement en direct")

### <a name="production"></a>Productions
L’entrée vidéo est le fondement de l’événement en direct et peut varier d’une webcam unique à une production vidéo professionnelle multicaméra. Les événements en direct dans Microsoft 365 prennent en charge un vaste éventail de scénarios de production ; incluez un événement produit dans teams à l’aide d’une webcam ou d’un événement généré dans une application ou un appareil externe. Vous pouvez sélectionner ces options en fonction de la configuration requise et du budget de votre projet. Il existe deux façons de produire des événements :

- **Teams**: ce mode de production permet aux utilisateurs de produire leurs événements en direct dans teams à l’aide de leur webcam ou en utilisant une entrée A/V à partir de systèmes de salle Teams. Cette option est l’option la plus rapide et la plus rapide si vous souhaitez utiliser les périphériques audio et vidéo connectés au PC ou inviter des présentateurs distants à participer à l’événement. Cette option permet aux utilisateurs d’utiliser facilement leurs webcams et de partager leurs écrans en tant qu’entrées dans l’événement. 

    ![Capture d’écran montrant un événement en direct généré à l’aide de la méthode de démarrage rapide](../media/teams-live-events-quick-start.png "Capture d’écran montrant un événement en direct qui est généré à l’aide du mode de production démarrage rapide")

- **Application ou appareil externe**: les codeurs externes permettent aux utilisateurs de produire leurs événements en direct à partir d’un matériel externe ou d’un codeur logiciel avec [flux](https://stream.microsoft.com). Cette option est idéale si vous disposez déjà d’un équipement de qualité de Studio (par exemple, des mixeurs multimédias) qui prend en charge la diffusion en continu vers un service de protocole de messagerie en temps réel (RTMP). Ce type de production est généralement utilisé dans des événements à grande échelle tels que le Directoire d’encadrement, dans lequel un flux unique d’un mélangeur de média est diffusé aux participants. 

    ![Capture d’écran montrant un événement en direct obtenu à l’aide d’une application ou d’un appareil externe](../media/teams-live-events-external-encoder.png "Capture d’écran montrant un événement en direct qui est réalisé à l’aide de la méthode de production d’une application ou d’un appareil externe")

### <a name="streaming-platform"></a>Plateforme en flux continu
La plateforme de flux d’événements en direct se compose des éléments suivants :

- **Services Azure Media**: [Azure Media Services](https://docs.microsoft.com/azure/media-services/previous/) vous permet d’accéder à des services de diffusion vidéo en continu pour atteindre des audiences plus importantes sur les appareils mobiles les plus populaires du jour. Media Services permet d’améliorer l’accessibilité, la distribution et l’évolutivité, et de faciliter et de rendre plus rentables le contenu de flux vers vos audiences locales ou internationales, tout en protégeant votre contenu.
- **Réseau de distribution de contenu (CDN) Azure**: une fois que votre flux est actif, il est transmis via le [réseau de distribution de contenu (CDN) Azure](https://docs.microsoft.com/azure/cdn/). Azure Media Services fournit un CDN intégré pour les points de terminaison en flux continu. Cela permet d’afficher les flux partout dans le monde sans mise en mémoire tampon.

### <a name="enterprise-content-delivery-network-ecdn"></a>Réseau de distribution de contenu d’entreprise (eCDN)
L’objectif de eCDN est de prendre le contenu vidéo à partir d’Internet et de distribuer le contenu au sein de votre entreprise, sans affecter les performances du réseau. Vous pouvez utiliser l’un des partenaires eCDN certifiés suivants pour optimiser votre réseau en ce qui concerne les événements dynamiques organisés au sein de votre organisation :
- [Ruche](https://www.hivestreaming.com/partners/integration-partners/microsoft/)
- [Kollective](https://kollective.com/ecdn-solutions/microsoft-live-events/)
- [Renforcement](http://www.ramp.com)

### <a name="attendee-experience"></a>Compétences des participants 
L’utilisation des participants est l’aspect le plus important des événements en direct et il est essentiel que les participants puissent participer à l’événement en direct sans problèmes. L’expérience des participants utilise le lecteur de flux (pour les événements produits dans Teams) et le lecteur multimédia Azure (pour les événements produits dans une application ou un appareil externe) et fonctionne sur les ordinateurs de bureau, les navigateurs et les appareils mobiles (iOS, Android). Microsoft 365 et Office 365 fournissent Yammer et teams sous la forme de deux hubs de collaboration et l’environnement des participants est intégré à ces outils de collaboration. 

![Capture d’écran montrant l’expertise des événements en direct](../media/teams-live-events-attendee.png "Capture d’écran montrant l’expertise des événements en direct")

### <a name="live-event-usage-report"></a>Rapport sur l’utilisation des événements en direct 
Les administrateurs de clients peuvent afficher les données d’analyse en temps réel des événements en direct dans le centre d’administration Microsoft Teams.  Le [rapport d’utilisation des événements en direct](../teams-analytics-and-reports/teams-live-event-usage-report.md) montre la vue d’ensemble de l’activité des événements en direct organisés au sein de l’organisation.  Les administrateurs peuvent afficher les informations d’utilisation des événements, notamment l’état des événements, l’heure de début, les vues et le type de production.  

## <a name="next-steps"></a>Étapes suivantes
Accédez au [plan pour les événements en direct teams](plan-for-teams-live-events.md).

### <a name="related-topics"></a>Rubriques connexes
- [Événements en direct sur Microsoft 365 dans Yammer, Microsoft teams et Microsoft Stream](https://docs.microsoft.com/stream/live-event-m365)
- [Commencer à utiliser Microsoft teams Live Events](https://support.office.com/article/d077fec2-a058-483e-9ab5-1494afda578a)
- [Événements en direct dans Yammer](https://support.office.com/article/live-events-in-yammer-4ece0ee2-c268-4636-bf2a-16e454befe57)
- [Événements en direct dans Microsoft Stream](https://docs.microsoft.com/stream/live-event-overview)

 
