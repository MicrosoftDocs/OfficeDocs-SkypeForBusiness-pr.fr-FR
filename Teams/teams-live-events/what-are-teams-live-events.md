---
title: Quelles sont les Teams Microsoft live événements ?
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: tonysmit
search.appverid: MET150
description: Découvrez comment live événements permettent aux utilisateurs de diffusion vidéo et de contenu à grande audiences en ligne dans Microsoft Teams, Yammer et Microsoft Stream.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 881d5c2754703766cb9b84525472bfa18fc6e651
ms.sourcegitcommit: 2e9761a3b195d31080bff3c9cc17a18adcd5350e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2018
ms.locfileid: "25748140"
---
# <a name="what-are-microsoft-teams-live-events"></a>Quelles sont les Teams Microsoft live événements ?
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

## <a name="overview"></a>Vue d’ensemble

Événements live Teams Microsoft, les utilisateurs de votre organisation peuvent diffuser le contenu de réunion et vidéo grand public en ligne. 

Événements en direct Microsoft 365 mettez vidéo en direct à un nouveau niveau, en privilégiant une connexion tout au long du cycle de vie mission avec les participants avant, pendant et après les événements en direct. Vous pouvez créer un événement en direct où réside votre audience, équipe ou la Communauté, à l’aide de Microsoft Stream, Microsoft Teams, ou Yammer.  

Équipes assure la collaboration basée sur la conversation, appel, réunions et des événements live, donc vous pouvez développer l’audience de vos réunions. Événements live équipes est une extension de réunions d’équipes, permettant aux utilisateurs de diffusion de contenu de réunion et vidéo à un grand public en ligne. Ils sont destinés à un-à-plusieurs communications où l’hôte de l’événement entraîne les interactions et participation d’audience est principalement à visualiser le contenu partagé par l’hôte. Les participants peuvent voir l’événement direct ou enregistré dans Yammer, équipes et/ou Microsoft Stream et peuvent interagir avec les présentateurs à l’aide de modéré Q & A ou conversation Yammer. 

Les équipes live événements sont considérés comme étant la prochaine version de diffusion de réunion Skype et finira par remplacent les fonctionnalités fournies dans Skype réunion diffusion. Lors de la publication de la version d’évaluation d’événements en direct équipes, nous continuera prendre en charge de Skype réunion diffusion, sans interruption de service pour les événements de nouveau ou futurs. Toutefois, nous vous invitons à essayer équipes des événements en direct pour tirer parti de toutes les nouvelles fonctionnalités très intéressantes, y compris le partage d’écran, le nombre de participants et prise en charge des encodeurs matérielles et logicielles externes. 

Par conséquent, nous allons commencer. Tout d’abord, examinez le diagramme suivant qui présente les composants de niveau élevés impliquées dans 365 Microsoft les événements en direct et comment ils sont connectés. 

![Diagramme présentant les composants clés d’événements en direct, planification, de production, flux Microsoft plateforme, certifié fournisseurs tiers eCDN] (../media/teams-live-events.png  "Diagramme présentant les composants clés d’événements en direct, planification, de production, flux Microsoft plateforme, certifié fournisseurs tiers eCDN")

## <a name="key-components"></a>Principaux composants
Par conséquent, vous pouvez le voir dans l’image ci-dessus, il existe quatre composants clés qui sont utilisés avec les événements en temps réel dans les équipes.

### <a name="scheduling"></a>La planification
Les équipes offre la possibilité pour les organisateurs créer un événement avec le participant approprié des autorisations, désigner les événements membres de l’équipe, sélectionnez la méthode de production et inviter des participants. Si l’événement live a été créé à partir d’un groupe de Yammer, les participants direct sera en mesure d’utiliser Yammer conversation pour interagir avec des personnes dans l’événement. 

![Capture d’écran montrant la nouvelle live écran événements pour créer et planifier un événement live] (../media/teams-live-events-schedule.png "Capture d’écran montrant la nouvelle live écran d’événement pour créer et planifier un événement live")

### <a name="production"></a>Production
Les événements dans 365 Microsoft live prend en charge un large éventail de scénarios de production, incluez un événement de démarrage rapide à l’aide des webcams ou d’un événement de codage externe à l’aide d’équipement de qualité studio. L’entrée vidéo est la base des événements Live et il peut varier d’une webcam doit être unique à une production vidéo professionnelle caméra multiple. Vous pouvez choisir de ces options en fonction de leurs besoins du projet et de votre budget. Il existe deux façons de générer des événements :

- **Démarrage rapide de production**: la méthode de production de démarrage rapide permet aux utilisateurs de créer leurs événements en direct à l’aide de réunions d’équipes. Cette option est idéale et une option plus rapide si vous souhaitez utiliser les périphériques audio et vidéos connecté à l’ordinateur ou invitez des présentateurs à distance pour participer à l’événement. Cette option permet aux utilisateurs d’utiliser leurs webcams facilement et de partager leur écran comme entrée dans l’événement. 

    ![Capture d’écran montrant un événement live, obtenue par l’utilisation rapide start, méthode de production] (../media/teams-live-events-quick-start.png "Capture d’écran montrant un événement qui est généré à l’aide rapide en direct start, méthode de production")

- **Production de codage externe**: encodeurs externes permettent aux utilisateurs de créer leurs événements directement à partir d’un matériel externe ou un encodeur basé sur logiciel avec [Flux Microsoft](https://stream.microsoft.com)live. Cette option est recommandée si vous disposez déjà d’équipement de qualité studio (par exemple, le mixage media) les prise en charge de la diffusion en continu à un service RTMP (Real-Time Messaging Protocol). Ce type de production est généralement utilisé dans les événements à grande échelle telles que des conférences entre les cadres – où un flux unique à partir d’un mixage multimédia est diffusée à l’audience. 

    ![Capture d’écran montrant un événement live généré à l’aide de la méthode de production de codage externe] (../media/teams-live-events-external-encoder.png "Capture d’écran montrant un événement qui est généré à l’aide de la méthode de codage externe de production en direct")

### <a name="streaming-platform"></a>Plateforme de diffusion en continu
La plate-forme de diffusion en continu live événement est composée des éléments suivants :

- **Azure Media Services**: [Azure Media Services](https://docs.microsoft.com/azure/media-services/previous/) vous permet de qualité de la diffusion des services de diffusion en continu vidéo pour atteindre le plus grand public sur les appareils mobiles les plus populaires d’aujourd'hui. Media Services améliore l’accessibilité, de distribution et l’évolutivité et rend facile et économique en continu dans votre magasin local ou dans le monde entier, tout en protégeant votre contenu.
- **Azure réseau CDN (Content Delivery)**: une fois votre flux de données publié, il est fourni par le biais du [Azure réseau CDN (Content Delivery)](https://docs.microsoft.com/azure/cdn/). Azure Media Services fournit CDN intégrée pour transmettre en continu des points de terminaison. Ainsi, pour les flux de données à afficher dans le monde entier avec aucune mise en mémoire tampon.

### <a name="enterprise-content-delivery-network-ecdn"></a>Enterprise Content Delivery Network (eCDN)
L’objectif d’eCDN consiste à prendre le contenu vidéo à partir d’internet et distribuer le contenu dans toute l’entreprise sans affecter les performances réseau. Vous pouvez utiliser une des options suivantes eCDN partenaires certifiés pour optimiser votre réseau pour les événements live organisées au sein de votre organisation :
- [Ruche](https://www.hivestreaming.com/partners/integration-partners/microsoft/)
- [Kollective](http://www.kollective.com)
- [Ramp](http://www.ramp.com)

### <a name="attendee-experience"></a>Expérience de participant 
L’expérience de participant est le plus important d’événements en direct et il est fondamental que les participants peuvent participer à l’événement live sans avoir des problèmes. L’expérience de participant utilise le lecteur Media Azure et fonctionne sur le bureau, navigateur et mobile (Android, iOS). Office 365 propose Yammer et les équipes deux concentrateurs de collaboration, ainsi que le participant live expérience est intégrée à ces outils de collaboration. 

![Expérience de capture d’écran montrant le participant d’événements en direct] (../media/teams-live-events-attendee.png "Expérience de capture d’écran montrant le participant d’événements en direct")

## <a name="next-steps"></a>Étapes suivantes
Accédez à [planifier des équipes événements en direct](plan-for-teams-live-events.md).

### <a name="related-topics"></a>Rubriques connexes
- [Événements en direct entre Microsoft 365 dans Yammer et Microsoft Stream Microsoft Teams](https://docs.microsoft.com/stream/live-event-m365)
- [Événements en direct dans Microsoft Teams](https://support.office.com/article/microsoft-teams-live-event-overview-d077fec2-a058-483e-9ab5-1494afda578a)
- [Événements en direct dans Yammer](https://support.office.com/article/live-events-in-yammer-4ece0ee2-c268-4636-bf2a-16e454befe57)
- [Événements en direct dans Microsoft Stream](https://docs.microsoft.com/stream/live-event-overview)

 
