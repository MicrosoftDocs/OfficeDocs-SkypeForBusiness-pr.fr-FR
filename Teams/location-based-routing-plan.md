---
title: Planifier le routage géodépendant pour le routage direct
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: roykuntz
search.appverid: MET150
description: Découvrez comment planifier le routage en fonction de l’emplacement pour le routage direct.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: ec48927559f5b10cbd8fec98966f1c55d0297fd2
ms.sourcegitcommit: 0e96539e3efef21ae6150f541efaeca3f9149aea
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/24/2020
ms.locfileid: "46864578"
---
# <a name="plan-location-based-routing-for-direct-routing"></a>Planifier le routage géodépendant pour le routage direct

## <a name="overview-of-location-based-routing"></a>Vue d’ensemble du routage par emplacement

Dans certains pays et certaines régions, il est illégal d’ignorer le fournisseur de réseau téléphonique commuté (PSTN) pour réduire les frais d’appel longue distance. Cet article décrit comment utiliser le routage basé sur l’emplacement pour limiter le recours au contournement pour les utilisateurs de Microsoft teams en fonction de leur emplacement géographique. Cet article s’applique uniquement au routage direct du système téléphonique.

Vous trouverez ci-dessous un aperçu du routage et des recommandations en fonction de l’emplacement pour vous aider à planifier la mise en route. Lorsque vous êtes prêt à appliquer et activer le routage selon l’emplacement, voir :

- [Déploiement des paramètres réseau pour le routage de géolocalisation](location-based-routing-configure-network-settings.md)
- [Activer le routage géodépendant pour le routage direct](location-based-routing-enable.md)

> [!NOTE]
> Le routage basé sur la géolocalisation n’est pas disponible dans les déploiements Microsoft 365 Government Community Cloud (GCC) High ou DoD.

Le routage basé sur l’emplacement est une fonctionnalité qui vous permet de limiter le contournement payant en fonction de la stratégie et de l’emplacement géographique de l’utilisateur au moment d’un appel RTC entrant ou sortant. Le routage basé sur l’emplacement est conçu pour fournir un mécanisme permettant d’éviter le contournement du numéro. Il ne doit pas être utilisé en tant que mécanisme pour diriger dynamiquement les appels RTC en fonction de l’emplacement de l’utilisateur ou d’éventuelles conséquences inattendues.

Lorsqu’un utilisateur de teams est activé pour le routage géolocalisation, les conditions suivantes s’appliquent :

- Pour passer un appel RTC sortant, l’une des conditions suivantes doit être remplie :
    - Le point de terminaison de l’utilisateur se trouve dans un site réseau activé pour le routage de géolocalisation et pour les appels sortants via la passerelle correspondante activée pour le routage sur site. 
    - Le point de terminaison de l’utilisateur se trouve dans un site réseau qui n’est pas activé pour le routage de géolocalisation et pour les appels sortants via une passerelle qui n’est pas activée pour le routage sur site.

    Les appels sortants ne sont pas autorisés dans un autre cas.

- Pour recevoir un appel RTC entrant, le point de terminaison de l’utilisateur doit se trouver dans le même site réseau où l’appel passe par la passerelle activée pour le routage par emplacement. Dans n’importe quel autre scénario, par exemple si l’utilisateur effectue une itinérance, l’appel n’est pas autorisé et est acheminé vers les paramètres de transfert d’appel de l’utilisateur (généralement la boîte vocale).
- Pour transférer un appel RTC vers un autre utilisateur de teams, le point de terminaison de l’utilisateur cible doit se trouver dans le même site réseau que l’utilisateur qui initialise le transfert. Les transferts ne sont pas autorisés dans un autre cas. 
- Pour transférer un autre utilisateur de teams vers le RTC, l’appel doit être transféré par le biais d’une passerelle de routage basée sur l’emplacement située sur le même site réseau que l’appelant initial. Les transferts ne sont pas autorisés dans un autre cas.

Le routage basé sur l’emplacement utilise les mêmes zones de réseau, de site et de sous-réseau que celles utilisées par Skype entreprise Server. Lorsque le contournement du péage est limité à un emplacement, un administrateur associe chaque sous-réseau IP et chaque passerelle PSTN pour cet emplacement à un site réseau. L’emplacement d’un utilisateur est déterminé par le sous-réseau IP auquel sont connectés les points de terminaison teams de l’utilisateur au moment de l’appel RTC. Un utilisateur peut avoir plusieurs clients teams situés sur différents sites, dans lesquels le routage de l’emplacement selon l’emplacement applique le routage de chaque client séparément selon l’emplacement de son point de terminaison. 

Pour vous familiariser avec la terminologie du réseau utilisée dans cet article, consultez la rubrique [paramètres réseau pour les fonctionnalités vocales dans teams](cloud-voice-network-settings.md).

## <a name="apply-location-based-routing"></a>Appliquer le routage par emplacement

Vous devez appliquer le routage sur site aux utilisateurs, aux sites réseau et aux passerelles RTC.  

### <a name="apply-location-based-routing-at-the-user-location"></a>Appliquer le routage par emplacement à l’emplacement de l’utilisateur

Comme mentionné plus haut, le routage basé sur l’emplacement s’applique uniquement aux utilisateurs qui sont configurés pour le routage direct. Le routage basé sur l’emplacement ne s’applique pas aux utilisateurs qui sont configurés pour le plan d’appels. Les utilisateurs doivent être activés pour le routage basé sur l’emplacement s’ils sont soumis à une restriction de contournement par le biais du contournement, qui contrôle les conditions dans lesquelles ils peuvent émettre et recevoir des appels RTC et la passerelle RTC qui peut être utilisée. Lorsqu’un utilisateur qui est autorisé à utiliser le routage de géolocalisation est situé sur un site activé pour le routage sur la base de l’emplacement, l’utilisateur doit appeler une passerelle basée sur l’emplacement connectée au site. 

Le routage en fonction de l’emplacement fonctionne en déterminant la localisation actuelle de l’utilisateur en fonction de l’adresse IP du point de terminaison d’équipe de l’utilisateur et en appliquant les règles en conséquence. L’emplacement d’un utilisateur qui est activé pour le routage par emplacement peut être classé comme suit : 
- **L’utilisateur se trouve sur le même site activé pour le routage sur l’emplacement que sur la passerelle RTC, où il a été attribué.**<br>Dans ce scénario, l’utilisateur se trouve dans un site réseau connu activé pour le routage par emplacement et le numéro de téléphone à l’intérieur de l’utilisateur s’arrête sur une passerelle PSTN qui se trouve sur le même site réseau. Par exemple, l’utilisateur se trouve au bureau. 
- **L’utilisateur se trouve sur un autre site activé pour le routage de l’emplacement non associé à la passerelle RTC et son inattribution.**<br>Dans ce scénario, l’utilisateur se trouve dans un site réseau connu activé pour le routage géolocalisation et ce site n’est pas associé à la passerelle RTC dans laquelle le numéro de l’utilisateur a été attribué. Par exemple, l’utilisateur se déplace vers un autre bureau.  
- **L’utilisateur se trouve sur un site interne qui n’est pas activé pour le routage par emplacement.** <br>Dans ce scénario, l’utilisateur se trouve dans un site réseau interne connu qui n’est pas activé pour le routage par emplacement. 
- **L’utilisateur se trouve sur un site inconnu.** 
    - L’utilisateur se trouve sur le réseau interne qui n’est pas défini comme site réseau. 
    - L’utilisateur se trouve en dehors du réseau interne. Par exemple, l’utilisateur se trouve sur Internet chez vous ou dans un café. 

### <a name="apply-location-based-routing-at-the-network-site"></a>Appliquer le routage géolocalisation sur le site réseau 
Les sites réseau doivent être activés pour le routage basé sur l’emplacement pour déterminer les passerelles pour diriger les utilisateurs à l’aide de la fonction de routage basée sur l’emplacement en itinérance. Si un utilisateur qui est autorisé à utiliser le routage de géolocalisation passe à un site activé pour le routage de géolocalisation, seule la passerelle RTC activée pour le routage par emplacement sur ce site peut être utilisée pour les appels sortants. Si un utilisateur qui est autorisé à utiliser le routage de géolocalisation passe à un site qui n’est pas activé pour le routage de géolocalisation, toute passerelle non activée pour le routage au niveau de l’emplacement peut être utilisée pour les appels sortants.  

### <a name="apply-location-based-routing-at-the-pstn-gateway"></a>Appliquer le routage géolocalisation sur la passerelle RTC 

Les passerelles sont associées à des sites pour déterminer à quel emplacement un utilisateur est autorisé à utiliser le routage sur l’emplacement pour passer ou recevoir un appel RTC. Les passerelles doivent être activées pour le routage par emplacement pour s’assurer qu’elles sont soumises à des restrictions de contournement de type et ne peuvent pas être utilisées par les utilisateurs qui ne sont pas autorisés à utiliser le routage par emplacement. La même passerelle peut être associée à plusieurs sites et peut être configurée pour être activée pour le routage au niveau de l’emplacement ou non activée pour le routage par emplacement, en fonction du site.

## <a name="scenarios-for-location-based-routing"></a>Scénarios de routage géodépendant

Cette section décrit les différents scénarios de limitation du recours au contournement du numéro à l’aide du routage par emplacement et compare le mode de routage des appels pour les utilisateurs qui ne sont pas autorisés à utiliser le routage par emplacement avec les utilisateurs autorisés à utiliser le routage de géolocalisation.

- [Un utilisateur d’équipes place un appel sortant vers le RTC](#teams-user-places-an-outbound-call-to-the-pstn)
- [Un utilisateur de teams reçoit un appel entrant du RTC](#teams-user-receives-an-inbound-call-from-the-pstn)
- [L’utilisateur teams transfère ou transfère un appel vers un autre utilisateur de teams](#teams-user-transfers-or-forwards-call-to-another-teams-user)
- [Les utilisateurs teams transfèrent ou transfèrent l’appel au point de terminaison PSTN](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)
- [Sonnerie simultanée](#simultaneous-ringing)
- [Délégation](#delegation)

Le diagramme suivant présente les restrictions activées par le routage par emplacement dans chaque scénario. Les utilisateurs, les sites réseau et les passerelles activés pour le routage géolocalisation sont entourés d’une bordure. Utilisez le diagramme comme guide pour mieux comprendre le fonctionnement du routage basé sur l’emplacement dans chaque scénario.  

![Diagramme illustrant des scénarios de routage sur site](media/lbr-direct-routing.png "Diagramme illustrant des scénarios de routage sur site")

### <a name="teams-user-places-an-outbound-call-to-the-pstn"></a>Un utilisateur d’équipes place un appel sortant vers le RTC

#### <a name="user-not-enabled-for-location-based-routing"></a>Utilisateur non activé pour le routage par emplacement

Un utilisateur qui n’est pas autorisé à utiliser le routage de géolocalisation peut effectuer des appels sortants à l’aide de n’importe quelle passerelle sur n’importe quel site qui n’est pas activé pour le routage de géolocalisation par le biais de sa stratégie de routage vocale affectée. Toutefois, si une passerelle est activée pour le routage de l’emplacement, l’utilisateur ne peut pas passer d’appel sortant par le biais de la passerelle, même si elle est affectée à sa stratégie de routage vocale. Si l’utilisateur effectue une itinérance vers un site activé pour le routage de géolocalisation, il peut uniquement appeler les appels via leurs passerelles de routage normales qui ne sont pas activées pour le routage sur l’emplacement.
 
#### <a name="user-enabled-for-location-based-routing"></a>Utilisateur activé pour le routage par emplacement
En comparaison, le routage des appels sortants pour les utilisateurs qui sont activés pour le routage sur l’emplacement est affecté par l’emplacement réseau du point de terminaison de l’utilisateur. Le tableau suivant indique la façon dont le routage en fonction de l’emplacement affecte le routage des appels sortants de User1, en fonction de l’emplacement de User1. 

|Emplacement du point de terminaison User1  |Routage des appels sortants pour User1  |
|---------|---------|
|Site sur lequel l’utilisateur a été affecté, site activé pour le routage de géolocalisation (site1)      |Appels routés via une passerelle activée pour le routage de géolocalisation (GW1) au site1, en fonction de la stratégie de routage vocale de l’utilisateur         |
|Site différent de l’endroit où l’utilisateur a été attribué, site activé pour le routage géolocalisation (site2)    |Appels routés via une passerelle activée pour le routage de géolocalisation (GW2) sur le site2 d’itinérance, en fonction de la stratégie de routage vocale de l’utilisateur        |
|Site différent de l’endroit où l’utilisateur a été affecté, l’option site n’est pas activée pour le routage par emplacement (site3)  |Appels routés par le biais d’une passerelle qui n’est pas activé pour le routage géolocalisation sur le site qui n’est pas activé pour le routage de géolocalisation (GW3), en fonction de la stratégie de routage vocale de l’utilisateur       |
|Réseau interne inconnu (Location4)    |  Appel RTC non autorisé       |
|Réseaux externes inconnus (Location5)    | Appel RTC non autorisé        |

### <a name="teams-user-receives-an-inbound-call-from-the-pstn"></a>Un utilisateur de teams reçoit un appel entrant du RTC

#### <a name="user-not-enabled-for-location-based-routing"></a>Utilisateur non activé pour le routage par emplacement

Un utilisateur qui n’est pas activé pour le routage géolocalisation peut recevoir un appel entrant de la passerelle qui n’est pas activé pour le routage de géolocalisation à partir duquel le numéro qui lui est attribué est entrant. Si l’utilisateur effectue une itinérance sur un site qui n’est pas activé pour le routage géolocalisation, il peut toujours recevoir des appels par le biais de ses passerelles RTC normales.
  
#### <a name="user-enabled-for-location-based-routing"></a>Utilisateur activé pour le routage par emplacement

En comparaison, les utilisateurs activés pour le routage géolocalisation peuvent uniquement recevoir des appels entrants de la passerelle RTC auxquelles ils ont été attribués lorsqu’ils se trouvent sur le même site. Le tableau suivant indique comment User1 reçoit les appels entrants Lorsque User1 se déplace vers d’autres emplacements réseau. Si l’appel n’est pas acheminé au point de terminaison de l’utilisateur, il accède aux paramètres de transfert d’appel de l’utilisateur, si les paramètres sont configurés. En règle générale, il s’agit de la boîte vocale.  

|Emplacement du point de terminaison User1  |Routage des appels entrants vers User1  |
|---------|---------|
|Site sur lequel l’utilisateur a été affecté, site activé pour le routage de géolocalisation (site1)   | Appels routés vers un point de terminaison utilisateur1 dans site1        |
|Site différent de l’endroit où l’utilisateur a été attribué, site activé pour le routage géolocalisation (site2)    | Appels non routés vers les points de terminaison du site2        |
|Site différent de l’endroit où l’utilisateur a été affecté, l’option site n’est pas activée pour le routage par emplacement (site3)    | Appels non routés aux points de terminaison dans site3        |
|Réseau interne inconnu (Location4)   | Appels non routés aux points de terminaison dans Location4        |
|Réseaux externes inconnus (Location5)     | Appels non routés aux points de terminaison dans Location5        |

### <a name="teams-user-transfers-or-forwards-call-to-another-teams-user"></a>L’utilisateur teams transfère ou transfère un appel vers un autre utilisateur de teams

Lorsqu’un point de terminaison PSTN est impliqué, le routage géolocalisation analyse si un ou les deux utilisateurs sont activés pour le routage de l’emplacement et détermine si l’appel doit être transféré ou transféré en fonction de l’emplacement des deux points de terminaison. 
 
Le transfert d’appel nécessite que l’utilisateur à l’origine de l’appel ne réponde pas lors du transfert d’appel. Cela signifie que les appels peuvent être transférés même si User1 ne se trouve pas à un emplacement pour recevoir des appels entrants (le tableau suivant : le message d' [équipe reçoit un appel entrant de la part du RTC](#teams-user-receives-an-inbound-call-from-the-pstn) ) et les appels ne peuvent pas être transférés si User1 ne peut pas recevoir l’appel entrant. 

#### <a name="user-not-enabled-for-location-based-routing"></a>Utilisateur non activé pour le routage par emplacement

Un utilisateur qui n’est pas activé pour le routage géolocalisation peut transférer ou transférer des appels RTC vers d’autres utilisateurs qui ne sont pas autorisés à effectuer le routage sur la base de l’emplacement. En règle générale, l’utilisateur n’est pas autorisé à transférer ou transférer un appel RTC à un utilisateur qui est autorisé à utiliser le routage de géolocalisation dans la mesure où le routage de l’emplacement est disponible uniquement dans les passerelles de routage basées sur l’emplacement pour les appels PSTN. Il s’agit de l’exception qui consiste à activer l’itinérance d’un utilisateur sur un site qui n’est pas activé pour le routage basé sur l’emplacement. Dans ce scénario, l’appel transféré est autorisé.  

De même, un utilisateur qui n’est pas activé pour le routage géolocalisation ne peut recevoir qu’un transfert ou un appel RTC d’un autre utilisateur qui n’est pas activé pour le routage sur site. 

#### <a name="user-enabled-for-location-based-routing"></a>Utilisateur activé pour le routage par emplacement

En règle générale, le fait de transférer et de transférer les appels RTC entrants à partir d’une passerelle activée pour le routage par emplacement est autorisé uniquement si l’utilisateur cible est activé pour le routage géolocalisation et se trouve sur le même site. Dans le cas contraire, le transfert et le transfert d’appel n’est pas autorisé. 

Le tableau suivant indique si le transfert d’appel et le transfert d’appel sont autorisés, en fonction de l’emplacement de l’utilisateur cible. Dans cette table, User1, situé dans site1, initialise le transfert ou le transfert vers d’autres utilisateurs d’équipes qui sont également activés pour le routage géolocalisation et qui se trouvent à des emplacements différents.  

|Emplacement du point de terminaison d’utilisateur cible|User1 Initialise le transfert d’appel |User1 Initialise le transfert d’appel|
|---------|---------|---------|
|Même site réseau que l’initiateur (utilisateur2)|Acceptés|Acceptés|
|Site réseau différent, site activé pour le routage géolocalisation (utilisateur3)|Non autorisé|Non autorisé|
|Site réseau différent, le site n’est pas activé pour le routage sur site (User4)|Non autorisé|Non autorisé|
|Réseau interne inconnu (user5)| Non autorisé|Non autorisé|
|Réseaux externes inconnus (User6)| Non autorisé|Non autorisé|

### <a name="teams-user-transfers-or-forwards-call-to-pstn-endpoint"></a>Les utilisateurs teams transfèrent ou transfèrent l’appel au point de terminaison PSTN

#### <a name="user-not-enabled-for-location-based-routing"></a>Utilisateur non activé pour le routage par emplacement

- Transférer et transférer un appel PSTN vers un autre numéro RTC est autorisé. 
- Le transfert et le transfert d’un appel VOIP entrant vers le RTC doivent respecter les restrictions de contournement par le biais de l’appelant. 
    - Si l’appelant n’est pas activé pour le routage géolocalisation, il peut être transféré vers n’importe quelle passerelle RTC qui n’est pas activée pour le routage sur site.
    - Si l’appelant est activé pour le routage sur la base de l’emplacement, il peut uniquement être transféré vers une passerelle de routage basée sur l’emplacement située sur le même site réseau. 

#### <a name="user-enabled-for-location-based-routing"></a>Utilisateur activé pour le routage par emplacement

- Le transfert et le transfert d’un appel PSTN vers un autre numéro RTC doivent être routés de la même passerelle de routage basée sur l’emplacement que l’appel entrant a été reçu. 
- Le transfert et le transfert d’un appel VOIP entrant vers le RTC doivent respecter tant l’appelant que les restrictions de contournement par le biais de l’utilisateur. 
    - Si l’appelant n’est pas activé pour le routage géolocalisation, il peut être transféré vers n’importe quelle passerelle RTC qui n’est pas activée pour le routage sur site.
    - Si l’appelant est activé pour le routage sur la base de l’emplacement, il peut être transféré uniquement vers une passerelle de routage basée sur l’emplacement située sur le même site réseau.
 
Le tableau suivant décrit la façon dont le routage en fonction de l’emplacement affecte le routage d’un appel VOIP de User1 à site1 aux utilisateurs situés à des emplacements différents qui transfèrent ou transfèrent l’appel vers un point de terminaison PSTN.  

|Utilisateur déclenchant ou transférant un appel  |Transférer vers PSTN  |Transférer vers PSTN  |
|---------|---------|---------|
|Même site réseau, site activé pour le routage de géolocalisation (utilisateur2)   |Le transfert d’appel ne peut être routé qu’via le routage par emplacement activé Gateway1 au site1, en fonction de la politique de routage vocale User2's         |Le transfert d’appel ne peut être routé qu’via le routage par emplacement activé Gateway1 au site1, en fonction de la politique de routage vocale User2's         |
|Site réseau différent, site activé pour le routage géolocalisation (utilisateur3)    |Le transfert d’appel ne peut être routé qu’via le routage par emplacement activé Gateway1 au site1, en fonction de la politique de routage vocale User3's         |Le transfert d’appel ne peut être routé qu’via le routage par emplacement activé Gateway1 au site1, en fonction de la stratégie de routage vocale User3's         |
|Site réseau différent, le site n’est pas activé pour le routage sur site (User4)    |Le transfert d’appel ne peut être routé qu’via le routage par emplacement activé Gateway1 au site1, en fonction de la politique de routage vocale User4's         |Le transfert d’appel ne peut être routé qu’via le routage par emplacement activé Gateway1 au site1, en fonction de la stratégie de routage vocale User4's         |
|Réseau interne inconnu (user5)     |Le transfert d’appel ne peut être routé qu’via le routage par emplacement activé Gateway1 au site1, en fonction de la politique de routage vocale User5's         |Le transfert d’appel ne peut être routé qu’via le routage par emplacement activé Gateway1 au site1, en fonction de la stratégie de routage vocale User5's         |
|Réseaux externes inconnus (User6)   |Le transfert d’appel ne peut être routé qu’via le routage par emplacement activé Gateway1 au site1, en fonction de la politique de routage vocale User6's        |Le transfert d’appel ne peut être routé qu’via le routage par emplacement activé Gateway1 au site1, en fonction de la stratégie de routage vocale User6's         |

### <a name="simultaneous-ringing"></a>Sonnerie simultanée

Lorsqu’un utilisateur qui est activé pour le routage de géolocalisation reçoit un appel et qu’il a activé la sonnerie simultanée, le routage géolocalisation analyse l’emplacement de la partie de l’appel et les points de terminaison des parties appelées pour déterminer si l’appel doit être routé. Les sonneries simultanées suivent les mêmes règles d’emplacement que les transferts d’appels et les transferts. 

#### <a name="simultaneous-ringing-for-another-teams-user"></a>Sonnerie simultanée pour un utilisateur de teams

Le tableau suivant indique si le routage en fonction de l’emplacement autorise une sonnerie simultanée à différents utilisateurs pour un appel RTC entrant pour User1.

|Emplacement du point de terminaison d’utilisateur cible|Sonnerie simultanée  |
|---------|---------|
|Même site réseau que l’initiateur (utilisateur2)   |Acceptés         |
|Site réseau en itinérance différent activé pour le routage géolocalisation (utilisateur3)   |Non autorisé         |
|Site réseau errant non activé pour le routage par emplacement (User4)   |Non autorisé        |
|Réseau interne inconnu (user5)    | Non autorisé        |
|Réseaux externes inconnus (User6)    |Non autorisé        |
|L’utilisateur cible est un numéro PSTN    |L’appel ne peut être routé qu’via le routage sur le Gateway1 à site1 sur le site1, en fonction de la stratégie de routage de la voix de utilisateur1.      |

#### <a name="simultaneous-ringing-to-a-pstn-endpoint"></a>Sonnerie simultanée d’un point de terminaison PSTN

Le tableau suivant indique le comportement de routage selon l’emplacement pour un appel VOIP entrant de User1 placé sur site1 aux utilisateurs situés à des emplacements différents avec un appel en parallèle configuré sur un numéro PSTN. 

|Intitulé emplacement du point de terminaison utilisateur  |La cible en anneau simultanée est Endpoint PSTN |
|---------|---------|
|Même site réseau, site activé pour le routage de géolocalisation (utilisateur2)    |L’appel peut être routé uniquement via le routage via le Gateway1 au site1, en fonction de la stratégie de routage vocale User2's       |
|Site réseau différent activé pour le routage de géolocalisation (utilisateur3)    |Les appels ne peuvent être routés qu’à l’aide du routage de Gateway1 au site1, en fonction de la stratégie de routage vocale User3's        |
|Autre site réseau non activé pour le routage par emplacement (User4)    |Les appels ne peuvent être routés qu’à l’aide du routage de Gateway1 au site1, en fonction de la stratégie de routage vocale User4's         |
|Réseau interne inconnu (user5)    |Les appels ne peuvent être routés qu’à l’aide du routage de Gateway1 au site1, en fonction de la stratégie de routage vocale User5's         |
|Réseaux externes inconnus (User6)   |Les appels ne peuvent être routés qu’à l’aide du routage de Gateway1 au site1, en fonction de la stratégie de routage vocale User6's         |

#### <a name="inbound-calls-through-voice-app-auto-attendant-or-call-queue"></a>Appels entrants via l’application vocale (standard automatique ou file d’attente d’appels)

Les appels RTC entrants à partir d’une passerelle prenant en charge le routage d’emplacement sont autorisés à se connecter à un standard automatique ou une file d’attente d’appels. Les utilisateurs activés pour le routage géolocalisation peuvent uniquement recevoir des appels entrants à partir de ces applications lorsqu’ils se trouvent sur le même site dont provient l’appel RTC entrant. 
 
Le transfert d’appel et la sonnerie simultanée aux utilisateurs et au RTC sont autorisés pour les transferts d’application vocale. L’appel de la cible est soumis aux mêmes règles de routage selon l’emplacement que celles indiquées plus haut.  
 
Le renvoi vers la boîte vocale est également autorisé.  

### <a name="delegation"></a>Délégation

Un utilisateur d’équipes peut choisir des délégués qui peuvent émettre et recevoir des appels en son nom. Les fonctionnalités de délégation dans teams sont affectées par le routage géolocalisation comme suit : 
- Pour les appels sortants à partir d’un délégué activé pour le routage de l’emplacement pour le compte d’un déléguer, les mêmes règles s’appliquent. Le routage des appels dépend de la stratégie d’autorisation des appels du délégué, de la stratégie de routage de la voix et de l’emplacement. Pour plus d’informations, reportez-vous [à la section l’utilisateur de teams place un appel sortant vers le RTC](#teams-user-places-an-outbound-call-to-the-pstn). 
- Pour les appels RTC entrants vers un déléguer, les mêmes règles de routage basées sur l’emplacement qui s’appliquent au transfert d’appel ou à la sonnerie simultanée à d’autres utilisateurs s’appliquent également aux délégués. Pour plus d’informations, reportez-vous à la section utilisateurs d’équipes transfère ou transfère un appel vers [un autre utilisateur de teams](#teams-user-transfers-or-forwards-call-to-another-teams-user), [teams transfère ou transfère un appel vers un point de terminaison PSTN](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)et [sonnerie simultanée](#simultaneous-ringing). Lorsqu’un délégué définit un point de terminaison PSTN en tant que cible de sonnerie simultanée, la stratégie de routage vocal du délégué est utilisée pour diriger l’appel vers le RTC. 
- Pour la délégation, il est recommandé de faire figurer la personne qui a délégué le message sur le même site réseau. 

## <a name="other-planning-considerations"></a>Autres considérations de planification

### <a name="changes-from-an-on-premises-location-based-routing-deployment"></a>Modifications d’un déploiement de routage local en local

La stratégie de routage vocal du site réseau n’est plus utilisée. À la place, nous utilisons la politique de routage vocale de l’utilisateur. En d’autres termes, pour permettre aux utilisateurs d’effectuer des déplacements vers d’autres sites, la stratégie de routage de la voix doit inclure les passerelles des sites errants. 

### <a name="technical-considerations-for-location-based-routing"></a>Considérations techniques relatives au routage géodépendant

Les sous-réseaux IPv4 et IPv6 sont pris en charge, cependant, le protocole IPv6 est prioritaire lors de la recherche d’une correspondance.

### <a name="client-support-for-location-based-routing"></a>Prise en charge du routage d’emplacement par le client

Les clients teams suivants sont pris en charge :
- Clients de bureau Teams (Windows et Mac)
- Clients mobiles Teams (iOS et Android)
- Téléphones IP teams

Le client Web teams et les clients Skype entreprise ne sont pas pris en charge.

### <a name="capabilities-not-supported-by-location-based-routing"></a>Fonctionnalités non prises en charge par le routage géodépendant

Le routage basé sur l’emplacement n’est pas applicable aux types d’interactions suivants. Le routage basé sur l’emplacement n’est pas appliqué lorsque les points de terminaison d’équipes interagissent avec les points de terminaison RTC dans les scénarios suivants : 
- Parcage d’appel ou récupération des appels via le parcage d’appels 
- Un utilisateur Skype entreprise sur site ou un utilisateur de Skype entreprise Online appelle un utilisateur de teams  

### <a name="location-based-routing-for-conferencing"></a>Routage basé sur l’emplacement pour les conférences

Un utilisateur de routage basé sur l’emplacement à l’aide d’un appel RTC n’est pas autorisé à démarrer une conférence avec un autre utilisateur ou numéro RTC. La connexion aux standards automatiques ou aux files d’attente d’appels est autorisée. Si l’utilisateur dispose d’une licence de conférence, l’utilisateur doit commencer une conférence avec les utilisateurs concernés et appeler le RTC via le pont de conférence pour démarrer une conférence téléphonique.  

### <a name="media-bypass-requirement-for-location-based-routing"></a>Exigence de contournement de média pour le routage par emplacement

Si vous déployez le routage de géolocalisation en Inde, il est nécessaire de configurer également une dérivation multimédia. Pour en savoir plus, consultez la section [planification de la dérivation multimédia avec le routage direct](direct-routing-plan-media-bypass.md) et l' [optimisation du contenu multimédia local pour le routage direct](direct-routing-media-optimization.md).

### <a name="direct-voice-over-ip-voip"></a>Voix sur IP (VoIP) directe

La voix sur IP (VoIP) directe ne doit pas être déployée avec un équipement de téléphonie en Inde.

## <a name="next-steps"></a>Étapes suivantes

Accédez à [configurer les paramètres réseau pour le routage selon l’emplacement](location-based-routing-configure-network-settings.md).

## <a name="related-topics"></a>Voir aussi

- [Activer le routage géodépendant pour le routage direct](location-based-routing-enable.md)
- [Paramètres réseau pour les fonctionnalités vocales de Cloud dans teams](cloud-voice-network-settings.md)
