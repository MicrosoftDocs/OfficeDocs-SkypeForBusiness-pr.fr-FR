---
title: Planifier le routage géodépendant pour le routage direct
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.service: msteams
ms.reviewer: roykuntz
search.appverid: MET150
description: Découvrez comment planifier le routage basé sur un emplacement pour le routage Direct.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8e6e8167dd6f543693638bed4fcbb467600364f0
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30461683"
---
# <a name="plan-location-based-routing-for-direct-routing"></a>Planifier le routage géodépendant pour le routage direct

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

## <a name="overview-of-location-based-routing"></a>Vue d’ensemble du routage basé sur l’emplacement

Dans certains pays et régions, il est interdit de contourner le fournisseur Public réseau de téléphonique commuté (RTC) pour réduire les coûts appel longue distances. Cet article décrit comment utiliser le routage basé sur un emplacement pour restreindre le contournement payant pour les utilisateurs de Microsoft Teams en fonction de leur emplacement géographique. Cet article s’applique uniquement à l’acheminement d’un système téléphonique Direct.

Ici, vous allez obtenir une vue d’ensemble du routage basé sur l’emplacement et des conseils pour vous aider à planifier. Lorsque vous êtes prêt à appliquer et activer le routage basé sur l’emplacement, voir :
- [Déployer les paramètres réseau pour le routage basé sur l’emplacement](location-based-routing-configure-network-settings.md)
- [Activer le routage géodépendant pour le routage direct](location-based-routing-enable.md)

Routage basé sur l’emplacement est une fonctionnalité qui permet de limiter la déviation du trafic payant basé sur la stratégie et la position géographique de l’utilisateur au moment d’un appel PSTN entrant ou sortant. 

Lorsqu’un utilisateur d’équipes est activé pour le routage basé sur l’emplacement, les éléments suivants s’applique :
- Pour émettre un appel RTC, une des options suivantes doit être remplie :
    - Point de terminaison de l’utilisateur se trouve dans un site réseau qui est activé pour la sortie de routage et les appels gÉodÉpendante par le biais de la passerelle correspondante est activée pour le routage basé sur l’emplacement. 
    - Point de terminaison de l’utilisateur se trouve dans un site réseau qui n’est pas activé pour le routage basé sur l’emplacement et appelle sortant via une passerelle n’est pas activée pour le routage basé sur l’emplacement.

    Les appels sortants ne sont pas autorisés dans n’importe quel autre scénario.

- Pour recevoir un appel RTC entrant, le point de terminaison répondeur automatique de l’utilisateur doit se trouver dans le même site réseau où l’appel ingresses par le biais de la passerelle est activé pour le routage basé sur l’emplacement. Dans n’importe quel autre scénario, par exemple, si l’utilisateur est itinérant, l’appel n’est pas autorisée et est routé vers (généralement messagerie vocale) les paramètres de transfert d’appel de l’utilisateur.
- Pour transférer un appel PSTN vers un autre utilisateur d’équipes, la cible de point de terminaison de l’utilisateur doit se trouver dans le même site réseau que l’utilisateur qui démarre le transfert. Transferts ne sont pas autorisés dans n’importe quel autre scénario. 
- Pour transférer un autre utilisateur équipes au réseau RTC, l’appel doit être transféré via une passerelle de routage gÉodÉpendante activé située sur le même site réseau que l’appelant initial. Transferts ne sont pas autorisés dans n’importe quel autre scénario.

Routage basé sur l’emplacement utilise les même réseau région, site et sous-réseau définitions Skype pour Business Server utilise. Lors de la déviation payant est limitée à un emplacement, un administrateur qui associe chaque sous-réseau IP et chaque passerelle PSTN à cet emplacement à un site réseau. Emplacement de l’utilisateur est déterminée par le sous-réseau IP connectés à points de terminaison équipes de l’utilisateur au moment de l’appel PSTN. Un utilisateur peut avoir plusieurs clients équipes situés dans différents sites, auquel cas routage basé sur l’emplacement impose de chaque client routage séparément selon l’emplacement de son point de terminaison. 

Pour vous familiariser avec la terminologie réseau utilisés dans cet article, voir [terminologie routage basé sur l’emplacement](location-based-routing-terminology.md).

## <a name="apply-location-based-routing"></a>Appliquer le routage basé sur l’emplacement

Vous devez appliquer le routage basé sur l’emplacement pour les utilisateurs, les sites de réseau et les passerelles PSTN.  

### <a name="apply-location-based-routing-at-the-user-location"></a>Appliquer l’emplacement de routage à l’emplacement de l’utilisateur

Comme mentionné précédemment, routage basé sur l’emplacement s’applique uniquement aux utilisateurs qui sont configurés pour le routage Direct. Routage basé sur l’emplacement ne s’applique pas aux utilisateurs qui sont configurés pour planifier l’appel. Les utilisateurs doivent être activés pour le routage basé sur l’emplacement s’ils sont sous restriction payant contournement de média, qui contrôle les conditions dans lesquelles ils peuvent émettre et recevoir des appels PSTN et la passerelle PSTN qui peut être utilisée. Lorsqu’un utilisateur qui est activé pour le routage basé sur l’emplacement se trouve sur un site qui a activé pour le routage basé sur l’emplacement, l’utilisateur doit effectuer des appels via une passerelle de routage basée sur l’emplacement activé connecté au site. 

Routage basé sur l’emplacement détermine l’emplacement actuel de l’utilisateur en fonction de l’adresse IP du point de terminaison des équipes de l’utilisateur et applique les règles en conséquence. L’emplacement d’un utilisateur qui est activé pour le routage basé sur l’emplacement peut être classée comme suit : 
- **L’utilisateur se trouve sur le même site activé de routage basée sur l’emplacement associé à la passerelle PSTN où l’arrivée leur est attribuée.**<br>Dans ce scénario, l’utilisateur se trouve dans un site réseau connus qui est activé pour le routage basé sur l’emplacement et Direct Inward numérotation (DID l’utilisateur) nombre termine sur une passerelle PSTN qui se trouve dans le même site réseau. Par exemple, l’utilisateur est au bureau. 
- **L’utilisateur se trouve dans un autre site en fonction de routage activée non associé à une passerelle PSTN où l’arrivée leur est attribuée.**<br>Dans ce scénario, l’utilisateur se trouve dans un site réseau connus qui est activé pour le routage basé sur l’emplacement, et ce site n’est pas associé à la passerelle PSTN où numéro de l’arrivée de l’utilisateur est affecté. Par exemple, l’utilisateur se déplace vers un autre bureau.  
- **L’utilisateur se trouve dans un site interne qui n’est pas activé pour le routage basé sur l’emplacement.** <br>Dans ce scénario, l’utilisateur se trouve dans un site réseau interne connus qui n’est pas activé pour le routage basé sur l’emplacement. 
- **L’utilisateur se trouve dans un site inconnu.** 
    - L’utilisateur est situé dans le réseau interne qui n’est pas défini comme un site réseau. 
    - L’utilisateur se trouve en dehors du réseau interne. Par exemple, l’utilisateur est sur Internet à domicile ou dans un café. 

### <a name="apply-location-based-routing-at-the-network-site"></a>Appliquer en fonction de routage au niveau du site réseau 
Sites réseau doivent être activés pour le routage emplacement afin de déterminer les passerelles pour acheminer les utilisateurs en fonction de routage activée lors de l’itinérance. Si un utilisateur qui est activé pour le routage basé sur l’emplacement passe à un site qui est activé pour le routage basé sur l’emplacement, seulement la passerelle PSTN est activée pour le routage emplacement sur le site utilisable pour les appels sortants. Si un utilisateur qui est activé pour le routage basé sur l’emplacement passe à un site qui n’est pas activé pour le routage basé sur l’emplacement, toute passerelle n’est pas activé pour le routage basé sur l’emplacement utilisable pour les appels sortants.  

### <a name="apply-location-based-routing-at-the-pstn-gateway"></a>Appliquer en fonction de routage de la passerelle PSTN 

Les passerelles sont associés aux sites pour déterminer où un utilisateur qui est activé pour le routage basé sur l’emplacement peut se trouver lorsqu’ils émettre ou recevoir un appel RTC. Passerelles doivent être activés pour l’emplacement de routage pour vous assurer qu’il est sous restrictions de contournement payant et ne peut pas être utilisé par les utilisateurs qui ne sont pas activés pour le routage basé sur l’emplacement. La même passerelle peut être associée à plusieurs sites et peuvent être configuré pour être activé pour le routage basé sur l’emplacement ou pas activé pour le routage basé sur l’emplacement, en fonction du site. 

## <a name="scenarios-for-location-based-routing"></a>Scénarios de routage géodépendant

Cette section décrit les différents scénarios de restriction payant le contournement de média à l’aide de routage basé sur l’emplacement et compare la façon dont les appels sont routés pour les utilisateurs qui ne sont pas activés pour le routage basé sur l’emplacement avec les utilisateurs activés pour le routage basé sur l’emplacement.

- [Utilisateur équipes place un appel sortant vers le réseau RTC](#teams-user-places-an-outbound-call-to-the-pstn)
- [Utilisateur équipes reçoit un appel entrant à partir de la passerelle PSTN](#teams-user-receives-an-inbound-call-from-the-pstn)
- [Utilisateur équipes transfère ou transfère l’appel vers un autre utilisateur d’équipes](#teams-user-transfers-or-forwards-call-to-another-teams-user)
- [Utilisateur équipes transfère ou transfère l’appel au point de terminaison RTC](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)
- [Sonnerie simultanée](#simultaneous-ringing)
- [Délégation](#delegation)

Le diagramme suivant illustre les restrictions activées par emplacement de routage dans chaque scénario. Les utilisateurs, sites réseau et les passerelles qui sont activés pour le routage basé sur l’emplacement ont une bordure. Utilisez le diagramme comme un guide pour vous aider à comprendre comment basé sur l’emplacement de routage fonctionne dans chaque scénario.  

![Diagramme montrant les scénarios pour le routage basé sur l’emplacement] (media/lbr-direct-routing.png "Diagramme montrant les scénarios pour le routage basé sur l’emplacement")

### <a name="teams-user-places-an-outbound-call-to-the-pstn"></a>Utilisateur équipes place un appel sortant vers le réseau RTC

#### <a name="user-not-enabled-for-location-based-routing"></a>Utilisateur non activé pour le routage basé sur l’emplacement

Un utilisateur qui n’est pas activé pour le routage basé sur l’emplacement peut effectuer des appels sortants à l’aide de n’importe quel passerelle de tous les sites qui ne sont pas activé pour le routage de gÉodÉpendante par le biais de leur stratégie de routage voix affectées. Toutefois, si une passerelle est activée pour le routage basé sur l’emplacement, l’utilisateur ne peut pas passer des appels sortants via la passerelle même si elle est attribuée à sa stratégie de routage voix. Si l’utilisateur passe à un site qui est activé pour le routage basé sur l’emplacement, ils ne pouvant émettre des appels par le biais de leurs passerelles routage normales qui ne sont pas activés pour le routage basé sur l’emplacement.
 
#### <a name="user-enabled-for-location-based-routing"></a>Utilisateur activé pour le routage basé sur l’emplacement
En revanche, le routage des appels sortants pour les utilisateurs qui sont activés pour le routage basé sur l’emplacement est affecté par l’emplacement réseau du point de terminaison de l’utilisateur. Le tableau suivant indique comment gÉodÉpendante routage a une incidence sur le routage des appels sortants de User1, selon l’emplacement de User1. 

|Emplacement du point de terminaison User1  |Routage des appels sortants de l’utilisateur1  |
|---------|---------|
|Même site où l’arrivée de l’utilisateur est affectée, site activé pour le routage basé sur l’emplacement (Site1)      |Appel acheminé via la passerelle est activé pour le routage basé sur l’emplacement (GW1) au Site1, en fonction de la stratégie de routage voix de l’utilisateur         |
|Site différent où l’arrivée de l’utilisateur est affecté, site activé pour le routage basé sur l’emplacement (Site2)    |Appel acheminé via la passerelle est activé pour le routage basé sur l’emplacement (GW2) à l’itinérance Site2, en fonction de la stratégie de routage de voix de l’utilisateur        |
|Site différent où l’arrivée de l’utilisateur est affecté, site ne pas activé pour le routage basé sur l’emplacement (Site3)  |Appel acheminé via la passerelle n’est pas activé pour le routage de basée sur l’emplacement sur le site n’a pas été activé pour le routage basé sur l’emplacement (GW3), en fonction de la stratégie de routage de voix de l’utilisateur       |
|Réseau interne inconnue (Location4)    |  PSTN appelant non autorisée       |
|Réseau externe inconnu (Location5)    | PSTN appelant non autorisée        |

### <a name="teams-user-receives-an-inbound-call-from-the-pstn"></a>Utilisateur équipes reçoit un appel entrant à partir de la passerelle PSTN

#### <a name="user-not-enabled-for-location-based-routing"></a>Utilisateur non activé pour le routage basé sur l’emplacement

Un utilisateur qui n’est pas activé pour le routage basé sur l’emplacement peut recevoir un appel entrant à partir de la passerelle n’est pas activée pour le routage basé sur l’emplacement à partir de laquelle leur affecté numéro DID ingresses. Si l’utilisateur passe à un site qui n’est pas activé pour le routage basé sur l’emplacement, ils peuvent toujours recevoir des appels par le biais de leurs passerelles PSTN normales.
  
#### <a name="user-enabled-for-location-based-routing"></a>Utilisateur activé pour le routage basé sur l’emplacement

En revanche, les utilisateurs activés pour le routage basé sur l’emplacement peuvent recevoir uniquement les appels entrants de la passerelle PSTN que leur arrivée est affectée à lorsqu’ils se trouvent sur le même site. Le tableau suivant montre comment User1 reçoit les appels entrants lorsque User1 déplace vers différents emplacements réseau. Si l’appel n’est pas acheminé vers le point de terminaison de l’utilisateur, il accède à, les paramètres de transfert d’appel de l’utilisateur si les paramètres sont configurés. En règle générale, il s’agit de la messagerie vocale.  

|Emplacement du point de terminaison User1  |Routage des appels entrants destinés à User1  |
|---------|---------|
|Même site où l’arrivée de l’utilisateur est attribué, site activé pour le routage basé sur l’emplacement (Site1)   | Appels acheminés vers le point de terminaison de l’utilisateur1 dans le Site1        |
|Site différent où l’arrivée de l’utilisateur est affecté, site activé pour le routage basé sur l’emplacement (Site2)    | Appels ne pas acheminés vers les points de terminaison dans Site2        |
|Site différent où l’arrivée de l’utilisateur est affecté, site ne pas activé pour le routage basé sur l’emplacement (Site3)    | Appels ne pas acheminés vers les points de terminaison dans Site3        |
|Réseau interne inconnue (Location4)   | Appels ne pas acheminés vers les points de terminaison dans Location4        |
|Réseau externe inconnu (Location5)     | Appels ne pas acheminés vers les points de terminaison dans Location5        |

### <a name="teams-user-transfers-or-forwards-call-to-another-teams-user"></a>Utilisateur équipes transfère ou transfère l’appel vers un autre utilisateur d’équipes

Lorsqu’un point de terminaison RTC est impliqué, en fonction de routage analyse si un ou les deux utilisateurs sont activés pour le routage basé sur l’emplacement et détermine si l’appel doit être transféré ou transféré selon l’emplacement de deux points de terminaison. 
 
Transfert d’appel oblige l’utilisateur initiateur identifier l’appel pendant le transfert d’appel ne nécessite pas l’appel initial. Cela signifie que les appels peuvent être transférés même si User1 n’est pas à un emplacement pour recevoir entrant appelle (voir le tableau dans la section [utilisateur équipes reçoit un appel entrant sur le réseau téléphonique commuté](#teams-user-receives-an-inbound-call-from-the-pstn) ) et les appels ne peuvent pas être transférés si User1 est incapable de recevoir l’appel entrant. 

#### <a name="user-not-enabled-for-location-based-routing"></a>Utilisateur non activé pour le routage basé sur l’emplacement

Un utilisateur qui n’est pas activé pour le routage basé sur l’emplacement permettre transférer ou PSTN transférer des appels à d’autres utilisateurs qui ne sont pas activés pour le routage basé sur l’emplacement. L’utilisateur n’est généralement pas être autorisé à transférer ou transférer un appel RTC à un utilisateur qui est activé pour le routage basé sur l’emplacement, car le routage basé sur l’emplacement activé les utilisateurs sont généralement seulement autorisés à être situés au niveau des passerelles de routage basée sur l’emplacement activé pour PSTN appels. L’exception est lorsqu’un routage basé sur l’emplacement activé suit utilisateur à un site qui n’est pas activé pour le routage basé sur l’emplacement. Dans ce scénario, l’appel transféré est autorisé.  

De même, un utilisateur qui n’est pas activé pour le routage basé sur l’emplacement ne peut recevoir un transfert ou transféré appel PSTN à partir d’un autre utilisateur qui n’est pas activé pour le routage basé sur l’emplacement. 

#### <a name="user-enabled-for-location-based-routing"></a>Utilisateur activé pour le routage basé sur l’emplacement

En règle générale, transfert et le transfert d’appels PSTN entrants à partir d’une passerelle qui est activé pour le routage basé sur l’emplacement sont autorisé uniquement si l’utilisateur cible est activé pour le routage basé sur l’emplacement et se trouve sur le même site. Sinon, le transfert et le transfert d’appel n’est pas autorisée. 

Le tableau suivant indique si les transferts d’appel et de transfert d’appel sont autorisées, selon l’emplacement de l’utilisateur cible. Dans ce tableau, User1, situé dans le Site1, lance le transfert ou transférer à d’autres utilisateurs équipes qui sont également activées pour le routage basé sur l’emplacement et qui se trouvent dans des emplacements différents.  

|Emplacement de point de terminaison de l’utilisateur cible|User1 lance le transfert d’appel |User1 lance l’appel vers l’avant|
|---------|---------|---------|
|Même site réseau en tant qu’initiateur (User2)|Autorisé|Autorisé|
|Site de réseau différents, site activé pour le routage basé sur l’emplacement de (l’utilisateur 3)|Non autorisé|Non autorisé|
|Site de réseau différents, site ne pas activé pour le routage basé sur un emplacement (utilisateur 4)|Non autorisé|Non autorisé|
|Réseau interne inconnue (User5)| Non autorisé|Non autorisé|
|Réseau externe inconnu (User6)| Non autorisé|Non autorisé|

### <a name="teams-user-transfers-or-forwards-call-to-pstn-endpoint"></a>Utilisateur équipes transfère ou transfère l’appel au point de terminaison RTC

#### <a name="user-not-enabled-for-location-based-routing"></a>Utilisateur non activé pour le routage basé sur l’emplacement

- Transfert et le transfert d’un appel PSTN vers un autre numéro PSTN est autorisée. 
- Transfert et le transfert d’appel VOIP entrant vers le réseau RTC doivent respecter les restrictions de contournement payant de l’appelant. 
    - Si l’appelant n’est pas activé pour le routage basé sur l’emplacement, ils peuvent être transférés à toute passerelle PSTN qui n’est pas activé pour le routage basé sur l’emplacement.
    - Si l’appelant est activé pour le routage basé sur l’emplacement, ils peuvent uniquement être transférés vers une passerelle basée sur l’emplacement de routage activé située sur le même site réseau. 

#### <a name="user-enabled-for-location-based-routing"></a>Utilisateur activé pour le routage basé sur l’emplacement

- Transfert et le transfert d’un réseau RTC de trafic entrant vers un autre numéro PSTN doit être acheminé à la même passerelle routage gÉodÉpendante activée qui a reçu l’appel entrant sur. 
- Transfert et un VOIP entrant de transfert d’appel vers le réseau RTC doit respecter les deux l’appelant et payant de l’utilisateur appelé contourner les restrictions. 
    - Si l’appelant n’est pas activé pour le routage basé sur l’emplacement, ils peuvent être transférés à toute passerelle PSTN qui n’est pas activé pour le routage basé sur l’emplacement.
    - Si l’appelant est activé pour le routage basé sur l’emplacement, ils peuvent être transférés seulement vers une passerelle basée sur l’emplacement de routage activé située sur le même site réseau.
 
Le tableau suivant indique comment basé sur l’emplacement de routage affecte le routage d’un appel VOIP d’utilisateur1 à Site1 aux utilisateurs de différents emplacements transfert ou de transférer l’appel vers un point de terminaison RTC.  

|Utilisateur qui lance le transfert d’appel ou le transfert  |Transférer vers PSTN  |Transférer vers PSTN  |
|---------|---------|---------|
|Même site réseau, site activé pour le routage basé sur l’emplacement de (l’utilisateur 2)   |Appel de transfert ne peut être routé par le biais de routage basé sur l’emplacement activé Gateway1 à Site1, en fonction de la stratégie de routage voix l’utilisateur 2         |Peuvent transférer appel uniquement acheminé par le biais de routage basé sur l’emplacement activé Gateway1 à Site1, en fonction de la stratégie de routage voix l’utilisateur 2         |
|Site de réseau différents, site activé pour le routage basé sur l’emplacement de (l’utilisateur 3)    |Appel de transfert ne peut être routé par le biais de routage basé sur l’emplacement activé Gateway1 à Site1, en fonction de la stratégie de routage voix de User3         |Transférer les appels ne peuvent être routé par le biais de routage basé sur l’emplacement activé Gateway1 à Site1, en fonction de la stratégie de routage voix de User3         |
|Site de réseau différents, site ne pas activé pour le routage basé sur un emplacement (utilisateur 4)    |Appel de transfert ne peut être routé par le biais de routage basé sur l’emplacement activé Gateway1 à Site1, en fonction de la stratégie de routage voix d’utilisateur 4         |Transférer les appels ne peuvent être routé par le biais de routage basé sur l’emplacement activé Gateway1 à Site1, en fonction de la stratégie de routage voix d’utilisateur 4         |
|Réseau interne inconnue (User5)     |Appel de transfert ne peut être routé par le biais de routage basé sur l’emplacement activé Gateway1 à Site1, en fonction de la stratégie de routage voix de User5         |Transférer les appels ne peuvent être routé par le biais de routage basé sur l’emplacement activé Gateway1 à Site1, en fonction de la stratégie de routage voix de User5         |
|Réseau externe inconnu (User6)   |Appel de transfert ne peut être routé par le biais de routage basé sur l’emplacement activé Gateway1 à Site1, en fonction de la stratégie de routage voix de User6        |Transférer les appels ne peuvent être routé par le biais de routage basé sur l’emplacement activé Gateway1 à Site1, en fonction de la stratégie de routage voix de User6         |

### <a name="simultaneous-ringing"></a>Sonnerie simultanée

Lorsqu’un utilisateur qui est activé pour le routage basé sur l’emplacement est un appel et a sonnerie simultanée activée, en fonction de routage analyse l’emplacement de l’appelant et les points de terminaison des parties appelées pour déterminer si l’appel doit être acheminé. Sonnerie simultanée suit les mêmes règles basées sur l’emplacement de transfert d’appel et transfère. 

#### <a name="simultaneous-ringing-for-another-teams-user"></a>Sonnerie simultanée d’un autre utilisateur d’équipes

Le tableau suivant indique si routage basé sur l’emplacement autorise la sonnerie simultanée à différents utilisateurs d’un appel RTC entrant pour User1.

|Emplacement de point de terminaison de l’utilisateur cible|Sonnerie simultanée  |
|---------|---------|
|Même site réseau en tant qu’initiateur (User2)   |Autorisé         |
|Site différents réseaux itinérants activé pour le routage basé sur l’emplacement de (l’utilisateur 3)   |Non autorisé         |
|Site de réseau itinérants ne pas activé pour le routage basé sur un emplacement (utilisateur 4)   |Non autorisé        |
|Réseau interne inconnue (User5)    | Non autorisé        |
|Réseau externe inconnu (User6)    |Non autorisé        |
|L’utilisateur cible est un numéro RTC    |Appel ne peut être routé par le biais de routage basé sur l’emplacement activé Gateway1 à Site1, en fonction de la stratégie de routage voix utilisateur1      |

#### <a name="simultaneous-ringing-to-a-pstn-endpoint"></a>Sonnerie simultanée à un point de terminaison RTC

Le tableau suivant indique le comportement de routage basé sur l’emplacement d’un appel VOIP entrant à partir de User1 situé dans le Site1 aux utilisateurs dans des emplacements différents avec la sonnerie simultanée définie sur un numéro RTC. 

|Emplacement du point de terminaison utilisateur appelé  |Cible de la sonnerie simultanée est le point de terminaison RTC |
|---------|---------|
|Même site réseau, site activé pour le routage basé sur l’emplacement de (l’utilisateur 2)    |Appel peut uniquement être acheminés via Gateway1 de routage basée sur l’emplacement à Site1, en fonction de la stratégie de routage voix l’utilisateur 2       |
|Site réseau activé pour le routage basé sur l’emplacement de (l’utilisateur 3)    |Appel ne peut être routé par le biais de Gateway1 de routage basée sur l’emplacement à Site1, en fonction de la stratégie de routage voix de User3        |
|Site de réseau différents ne pas activé pour le routage basé sur un emplacement (utilisateur 4)    |Appel ne peut être routé par le biais de Gateway1 de routage basée sur l’emplacement à Site1, en fonction de la stratégie de routage voix d’utilisateur 4         |
|Réseau interne inconnue (User5)    |Appel ne peut être routé par le biais de Gateway1 de routage basée sur l’emplacement à Site1, en fonction de la stratégie de routage voix de User5         |
|Réseau externe inconnu (User6)   |Appel ne peut être routé par le biais de Gateway1 de routage basée sur l’emplacement à Site1, en fonction de la stratégie de routage voix de User6         |

#### <a name="inbound-calls-through-voice-app-auto-attendant-or-call-queue"></a>Appels entrants via application vocale (standard automatique ou la file d’attente des appels)

Appels PSTN entrants à partir d’une passerelle de routage basée sur l’emplacement activé sont autorisés à se connecter à une file d’attente standard ou un appel automatique. Les utilisateurs activés pour le routage basé sur l’emplacement peuvent uniquement recevoir les transferts d’appel entrant à partir de ces applications lorsqu’ils se trouvent sur le même site que provient l’appel PSTN entrant. 
 
Le transfert d’appel et la sonnerie simultanée pour les utilisateurs et PSTN est autorisée pour les transferts d’application vocale. Terminer l’appel vers la cible est soumis aux mêmes règles de routage basé sur l’emplacement indiqués précédemment.  
 
Transfert vers la messagerie vocale est également autorisé.  

### <a name="delegation"></a>Délégation

Les équipes utilisateur peut choisir des délégués peuvent émettre et recevoir des appels en son nom. Fonctionnalités de délégation d’équipes sont affectées par le routage basé sur l’emplacement comme suit : 
- Pour les appels sortants à partir d’un délégué en fonction de routage activée part d’une personne, les mêmes règles s’appliquent. Routage des appels est basé sur la stratégie d’autorisation des appels, la stratégie de routage voix et emplacement du délégué. Pour plus d’informations, voir [utilisateur équipes place un appel sortant vers le réseau RTC](#teams-user-places-an-outbound-call-to-the-pstn). 
- Pour les appels PSTN entrants à une personne, les mêmes règles de routage basé sur l’emplacement qui s’appliquent pour le transfert d’appel ou la sonnerie simultanée à d’autres utilisateurs s’applique également aux délégués. Pour plus d’informations, voir [ [utilisateur équipes transfère ou transfère l’appel vers un autre utilisateur d’équipes](#teams-user-transfers-or-forwards-call-to-another-teams-user), équipes utilisateur transfère ou transfère l’appel au point de terminaison RTC](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)et [sonnerie simultanée](#simultaneous-ringing). Lorsqu’un délégué définit un point de terminaison RTC comme cible de la sonnerie simultanée, la stratégie de routage voix du délégué sert à acheminer l’appel vers la passerelle PSTN. 
- Pour la délégation, il est recommandé que la personne qui a délégué et délégués associés se trouver dans le même site réseau. 

## <a name="other-planning-considerations"></a>Autres considérations de planification

### <a name="changes-from-an-on-premises-location-based-routing-deployment"></a>Modifications apportées à partir d’un déploiement de routage basé sur un emplacement local

Stratégie de routage voix site réseau n’est plus utilisé. Au lieu de cela, nous utilisons stratégie de routage voix de l’utilisateur. Cela signifie que, pour permettre aux utilisateurs de passer à d’autres sites, la stratégie de routage voix doit inclure les passerelles des sites itinérants. 

### <a name="technical-considerations-for-location-based-routing"></a>Considérations techniques relatives au routage géodépendant

Les sous-réseaux IPv4 et IPv6 sont prises en charge, toutefois, IPv6 est prioritaire lors de la vérification pour une correspondance. Prise en charge d’IPv6 est en cours et sera disponible par disponibilité générale pour le routage basé sur l’emplacement. 

### <a name="client-support-for-location-based-routing"></a>Prise en charge du client pour le routage basé sur l’emplacement

Les clients équipes suivants sont pris en charge :
- Clients de bureau équipes (Windows et Mac)
- Clients mobiles équipes (iOS et Android)
- Les équipes des téléphones IP

Le client web d’équipes et Skype pour les clients d’entreprise ne sont pas pris en charge.

### <a name="capabilities-not-supported-by-location-based-routing"></a>Fonctionnalités non prises en charge par le routage géodépendant

Routage basé sur l’emplacement ne s’applique pas aux types d’interactions suivants. Routage basé sur l’emplacement n’est pas appliquée lorsque les points de terminaison équipes interagissent avec les systèmes d’extrémité PSTN dans les scénarios suivants : 
- Parcage d’appel ou récupération des appels via le parcage d’appels 
- Un Skype sur site pour l’utilisateur d’entreprise ou un Skype pour Business Online utilisateur appelle un utilisateur d’équipes  

### <a name="location-based-routing-for-conferencing"></a>Emplacement de routage pour la conférence

Un utilisateur en fonction de routage activée sur un appel RTC n’est pas autorisé à démarrer une conférence avec un autre utilisateur ou un numéro RTC. Connexion à des standards automatiques ou des files d’attente de l’appel est autorisé. Si l’utilisateur possède une licence de conférence, l’utilisateur doit démarrer une conférence avec les utilisateurs concernés et appeler via le pont de conférence PSTN pour démarrer une téléconférence.  

## <a name="next-steps"></a>Étapes suivantes
Accédez à [configurer les paramètres réseau pour le routage basé sur l’emplacement](location-based-routing-configure-network-settings.md).

### <a name="related-topics"></a>Rubriques connexes
- [Activer le routage géodépendant pour le routage direct](location-based-routing-enable.md)
- [Terminologie du routage géodépendant](location-based-routing-terminology.md)