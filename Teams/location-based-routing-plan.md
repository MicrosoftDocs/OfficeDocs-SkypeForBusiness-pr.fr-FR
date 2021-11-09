---
title: Planifier le routage géodépendant pour le routage direct
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: roykuntz
search.appverid: MET150
description: Découvrez comment planifier Location-Based routage pour le routage direct.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 887fd7bf955f5caa76a0dde3b42b96b912f23355
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60829608"
---
# <a name="plan-location-based-routing-for-direct-routing"></a>Planifier le routage géodépendant pour le routage direct

## <a name="overview-of-location-based-routing"></a>Vue d’ensemble du Location-Based routage des lignes

Dans certains pays et certaines régions, il n’est pas illégal de contourner le fournisseur de réseau téléphonique commuté (PSTN) afin de diminuer les coûts des appels longue distance. Cet article décrit comment utiliser un routage Location-Based pour restreindre la dérivation contre les Microsoft Teams en fonction de leur emplacement géographique. Cet article s’applique uniquement Système téléphonique routage direct.

Vous obtenez ici une vue d’ensemble de Location-Based routage et des conseils pour vous aider à le planifier. Lorsque vous êtes prêt à appliquer et à activer Location-Based routage, voir :

- [Déployer les paramètres réseau pour le Location-Based routage](location-based-routing-configure-network-settings.md)
- [Activer le routage géodépendant pour le routage direct](location-based-routing-enable.md)

> [!NOTE]
> Location-Based routage n’est pas disponible dans Microsoft 365 Cloud de la communauté du secteur public (Cloud de la communauté du secteur public) en haut ou en dod.

Location-Based routage est une fonctionnalité qui vous permet de restreindre le contournement toll en fonction d’une stratégie et de l’emplacement géographique de l’utilisateur au moment d’un appel PSTN entrant ou sortant. Location-Based routage est conçu pour fournir un mécanisme permettant d’empêcher une dérivation contre les frais. Elle ne doit pas être utilisée comme mécanisme permettant de router dynamiquement des appels PSTN en fonction de l’emplacement de l’utilisateur, ou de conséquences inattendues.

Lorsqu’Teams utilisateur est activé pour lLocation-Based routage des données, les informations suivantes s’appliquent :

- Pour effectuer un appel PSTN sortant, l’une des valeurs suivantes doit être vraie :
    - Le point de terminaison de l’utilisateur est situé sur un site réseau activé pour le routage Location-Based et la sortie via la passerelle correspondante activée pour le Location-Based routage. 
    - Le point de terminaison de l’utilisateur est situé sur un site réseau qui n’est pas activé pour le routage Location-Based et la sortie des appels via une passerelle non activée pour le Location-Based routage.

    Les appels sortants ne sont pas autorisés dans tout autre scénario.

- Pour recevoir un appel PSTN entrant, le point de terminaison de réponse de l’utilisateur doit se trouver sur le même site réseau que celui où l’appel s’est produit via la passerelle activée pour le routage Location-Based ligne. Dans tout autre scénario, comme si l’utilisateur est en itinérance, l’appel n’est pas autorisé et est acheminé vers les paramètres de forwardage d’appel de l’utilisateur (généralement la messagerie vocale).
- Pour transférer un appel PSTN vers un autre utilisateur Teams, le point de terminaison de l’utilisateur cible doit se trouver sur le même site réseau que l’utilisateur qui déclenche le transfert. Les transferts ne sont pas autorisés dans tout autre scénario. 
- Pour transférer un autre utilisateur Teams vers le réseau PSTN, l’appel doit être transféré via une passerelle Location-Based routage située sur le même site réseau que l’appelant initial. Les transferts ne sont pas autorisés dans tout autre scénario.

Location-Based routage utilise les mêmes définitions de région réseau, de site et de sous-réseau que Skype Entreprise Server réseau. Lorsque la dérivation toll est limitée à un emplacement, un administrateur associe chaque sous-réseau IP et chaque passerelle PSTN pour cet emplacement à un site réseau. L’emplacement d’un utilisateur est déterminé par le sous-réseau IP à partir Teams points de terminaison de l’utilisateur, qui est connecté au moment d’un appel PSTN. Un utilisateur peut avoir plusieurs clients Teams situés sur différents sites, auquel cas le routage Location-Based applique le routage de chaque client séparément en fonction de l’emplacement de son point de terminaison. 

Pour vous familiariser avec la terminologie réseau utilisée dans cet article, consultez les paramètres réseau des [fonctionnalités vocales cloud dans Teams.](cloud-voice-network-settings.md)

## <a name="apply-location-based-routing"></a>Appliquer Location-Based routage

Vous devez appliquer Location-Based routage aux utilisateurs, aux sites réseau et aux passerelles RST.  

### <a name="apply-location-based-routing-at-the-user-location"></a>Appliquer Location-Based routage à l’emplacement de l’utilisateur

Comme mentionné précédemment, Location-Based routage s’applique uniquement aux utilisateurs qui sont configurer pour le routage direct. Location-Based routage ne s’applique pas aux utilisateurs qui sont configurer pour une forfait d’appels. Les utilisateurs doivent être activés pour l’acheminement Location-Based s’ils sont dans le cadre d’une restriction de dérivation contre les frais, ce qui contrôle les conditions dans lesquelles ils peuvent passer et recevoir des appels RSTN et la passerelle PSTN qui peut être utilisée. Lorsqu’un utilisateur activé pour l’acheminement Location-Based est situé sur un site pour le routage Location-Based, il doit passer des appels via une passerelle Location-Based routage connectée au site. 

Location-Based routage fonctionne en déterminant l’emplacement actuel de l’utilisateur en fonction de l’adresse IP du point de terminaison Teams de l’utilisateur et applique les règles en conséquence. L’emplacement d’un utilisateur activé pour Location-Based routage peut être classé de la manière suivante : 
- **L’utilisateur se trouve sur le même site Location-Based routage de routage associé à la passerelle PSTN à laquelle la stratégie DID est attribuée.**<br>Dans ce scénario, l’utilisateur est situé sur un site réseau connu pour le routage Location-Based et son numéro de numéro vers l’intérieur des utilisateurs se termine sur une passerelle RSTN qui se trouve sur le même site réseau. Par exemple, l’utilisateur est au bureau. 
- **L’utilisateur se trouve sur un autre site Location-Based routage n’est pas associé à la passerelle RSTN à laquelle la stratégie DID est attribuée.**<br>Dans ce scénario, l’utilisateur se trouve sur un site réseau connu activé pour le routage Location-Based et ce site n’est pas associé à la passerelle RSTN à laquelle est attribué le numéro DID de l’utilisateur. Par exemple, l’utilisateur se déplace vers un autre bureau.  
- **L’utilisateur se trouve sur un site interne qui n’est pas activé pour l'Location-Based routage.** <br>Dans ce scénario, l’utilisateur se trouve sur un site de réseau interne connu qui n’est pas activé Location-Based routage. 
- **L’utilisateur se trouve sur un site inconnu.** 
    - L’utilisateur se trouve au sein du réseau interne qui n’est pas défini en tant que site réseau. 
    - L’utilisateur est situé en dehors du réseau interne. Par exemple, l’utilisateur est sur Internet, chez lui ou dans un café. 

### <a name="apply-location-based-routing-at-the-network-site"></a>Appliquer Location-Based routage sur le site réseau 
Les sites réseau doivent être activés pour lLocation-Based routage afin d’aider à déterminer les passerelles à router Location-Based les utilisateurs à l’aide du routage en itinérance. Si un utilisateur activé pour l’acheminement Location-Based est en itinérance vers un site pour le routage Location-Based, seule la passerelle RN activée pour le routage Location-Based au niveau de ce site peut être utilisée pour les appels sortants. Si un utilisateur activé pour le routage Location-Based est en itinérance vers un site non activé pour le routage Location-Based, toute passerelle non activée pour le routage Location-Based peut être utilisée pour les appels sortants.  

### <a name="apply-location-based-routing-at-the-pstn-gateway"></a>Appliquer Location-Based routage à la passerelle PSTN 

Les passerelles sont associées aux sites pour déterminer où peut se trouver un utilisateur activé pour l’acheminement Location-Based lorsqu’il passe ou reçoit un appel PSTN. Les passerelles doivent être activées pour le routage Location-Based afin de s’assurer qu’elles font l’objet de restrictions de contournement toll et ne peuvent pas être utilisées par les utilisateurs qui ne sont pas activés pour l'Location-Based routage. La même passerelle peut être associée à plusieurs sites et elle peut être configurée pour être activée pour le routage Location-Based ou non pour le routage Location-Based, selon le site.

## <a name="scenarios-for-location-based-routing"></a>Scénarios de routage géodépendant

Cette section décrit différents scénarios de limitation de la dérivation toll à l’aide du routage Location-Based et compare la façon dont les appels sont acheminés pour les utilisateurs qui ne sont pas activés pour le routage Location-Based avec ceux qui sont activés pour le routage Location-Based.

- [Teams passe un appel sortant vers le PSTN](#teams-user-places-an-outbound-call-to-the-pstn)
- [Teams un utilisateur reçoit un appel entrant du PSTN](#teams-user-receives-an-inbound-call-from-the-pstn)
- [Teams transferts ou transferts d’appel vers un Teams utilisateur](#teams-user-transfers-or-forwards-call-to-another-teams-user)
- [Teams transferts ou transferts d’appel vers le point de terminaison PSTN](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)
- [Sonnerie simultanée](#simultaneous-ringing)
- [Délégation](#delegation)

Le diagramme suivant montre les restrictions activées par le Location-Based routage dans chaque scénario. Les utilisateurs, les sites réseau et les passerelles Location-Based pour le routage ont une bordure autour. Utilisez le diagramme comme guide pour vous aider à comprendre le fonctionnement Location-Based routage dans chaque scénario.  

![Diagramme montrant des scénarios d'Location-Based routage.](media/lbr-direct-routing.png "Diagramme montrant des scénarios d'Location-Based routage")

### <a name="teams-user-places-an-outbound-call-to-the-pstn"></a>Teams passe un appel sortant vers le PSTN

#### <a name="user-not-enabled-for-location-based-routing"></a>Utilisateur non activé pour l'Location-Based routage

Un utilisateur qui n’est pas activé pour le routage Location-Based peut passer des appels sortants à l’aide d’une passerelle sur n’importe quel site qui n’est pas activé pour le routage Location-Based par le biais de la stratégie de routage vocale qui lui est affectée. Toutefois, si une passerelle est activée pour le routage Location-Based, l’utilisateur ne peut pas passer d’appels sortants via la passerelle, même s’il est affecté à sa stratégie de routage vocal. Si l’utilisateur est en itinérance vers un site pour le routage Location-Based, il peut uniquement passer des appels via ses passerelles de routage normales qui ne sont pas activées pour le Location-Based routage.
 
#### <a name="user-enabled-for-location-based-routing"></a>Utilisateur activé pour l'Location-Based routage
En comparaison, le routage des appels sortants pour les utilisateurs activés pour le routage Location-Based est affecté par l’emplacement réseau du point de terminaison de l’utilisateur. Le tableau suivant indique la manière dont Location-Based routage affecte le routage des appels sortants de l’utilisateur 1, selon l’emplacement de l’utilisateur 1. 

|Emplacement du point de terminaison Utilisateur1  |Routage des appels sortants pour User1  |
|---------|---------|
|Même site sur lequel la dida pas d’utilisateur est attribuée, site activé Location-Based routage des tâches (Site1)      |Appel roué via une passerelle activée pour le routage Location-Based (GW1) sur site1, en fonction de la stratégie de routage voix de l’utilisateur         |
|Site différent de l’emplacement où est attribué le DID de l’utilisateur, site activé Location-Based routage (Site2)    |Appel roué via une passerelle activée pour Location-Based routage des appels (GW2) en itinérance site2, en fonction de la stratégie de routage voix de l’utilisateur        |
|Site différent de l’emplacement où est attribué le DID de l’utilisateur, le site n’est pas activé Location-Based routage (Site3)  |Appel acheminé via une passerelle non activée pour le routage Location-Based sur un site non activé pour le routage Location-Based (GW3), en fonction de la stratégie de routage vocale de l’utilisateur       |
|Réseau interne inconnu (Emplacement4)    |  Appels PSTN non autorisés       |
|Réseau externe inconnu (Emplacement5)    | Appels PSTN non autorisés        |

### <a name="teams-user-receives-an-inbound-call-from-the-pstn"></a>Teams un utilisateur reçoit un appel entrant du PSTN

#### <a name="user-not-enabled-for-location-based-routing"></a>Utilisateur non activé pour l'Location-Based routage

Un utilisateur qui n’est pas activé pour le routage Location-Based peut recevoir un appel entrant de la passerelle qui n’est pas activée pour le routage Location-Based à partir duquel les numéroters DID qui lui sont attribués. Si l’utilisateur est en itinérance vers un site qui n’est pas activé pour le routage Location-Based, il peut toujours recevoir des appels via ses passerelles PSTN normales.
  
#### <a name="user-enabled-for-location-based-routing"></a>Utilisateur activé pour l'Location-Based routage

En comparaison, les utilisateurs activés pour le routage Location-Based peuvent uniquement recevoir des appels entrants à partir de la passerelle RST À quoi ils ont participé lorsqu’ils se trouvent sur le même site. Le tableau suivant indique comment l’utilisateur1 reçoit des appels entrants lorsque l’utilisateur1 se déplace vers différents emplacements réseau. Si l’appel n’est pas acheminé vers le point de terminaison de l’utilisateur, il est transmis aux paramètres de l’utilisateur de forwardage d’appel, si les paramètres sont configurés. Il s’agit généralement de messages vocaux.  

|Emplacement du point de terminaison Utilisateur1  |Routage des appels entrants vers User1  |
|---------|---------|
|Site identique à l’emplacement où la dida passage de l’utilisateur est attribuée, site activé Location-Based routage des tâches (Site1)   | Appels acheminés vers le point de terminaison de l’utilisateur1 dans Site1        |
|Site différent de l’endroit où est attribué le didas de l’utilisateur, le site activé Location-Based routage des tâches (Site2)    | Appels non acheminés vers les points de terminaison dans Site2        |
|Site différent de l’emplacement où le DID de l’utilisateur est attribué, le site n’est pas activé Location-Based routage (Site3)    | Appels non acheminés vers les points de terminaison dans Site3        |
|Réseau interne inconnu (Emplacement4)   | Appels non acheminés vers les points de terminaison dans l’emplacement4        |
|Réseau externe inconnu (Emplacement5)     | Appels non acheminés vers les points de terminaison dans l’emplacement5        |

### <a name="teams-user-transfers-or-forwards-call-to-another-teams-user"></a>Teams transferts ou transferts d’appel vers un Teams utilisateur

Lorsqu’un point de terminaison RN est impliqué, le routage Location-Based analyse si un ou les deux utilisateurs sont activés pour le routage Location-Based et détermine si l’appel doit être transféré ou transféré en fonction de l’emplacement des deux points de terminaison. 
 
Le transfert d’appel nécessite que l’utilisateur à l’origine réponde à l’appel alors que le transfert d’appel ne nécessite pas de réponse à l’appel initial. Cela signifie que les appels peuvent être transférés même si l’utilisateur1 n’est pas à un emplacement pour recevoir des appels entrants (voir le tableau dans la section Teams l’utilisateur reçoit un appel entrant à partir de la section [PSTN)](#teams-user-receives-an-inbound-call-from-the-pstn) et les appels ne peuvent pas être transférés si l’utilisateur1 ne peut pas recevoir l’appel entrant. 

#### <a name="user-not-enabled-for-location-based-routing"></a>Utilisateur non activé pour l'Location-Based routage

Un utilisateur qui n’est pas activé pour l’acheminement Location-Based peut transférer ou transférer des appels RSTN vers d’autres utilisateurs qui ne sont pas activés pour l'Location-Based routage. En règle générale, l’utilisateur n’est pas autorisé à transférer ou transférer un appel PSTN à un utilisateur activé pour le routage Location-Based car les utilisateurs à l’ouverture d’un routage Location-Based sont en général autorisés uniquement à être situés sur des passerelles Location-Based routage pour les appels RSTN. L’exception concerne l'Location-Based d’un utilisateur activé pour le routage vers un site qui n’est pas activé Location-Based routage. Dans ce scénario, l’appel transféré est autorisé.  

De même, un utilisateur qui n’est pas activé pour le routage Location-Based peut uniquement recevoir un appel de transfert ou de transfert PSTN d’un autre utilisateur qui n’est pas activé pour l'Location-Based routage. 

#### <a name="user-enabled-for-location-based-routing"></a>Utilisateur activé pour l'Location-Based routage

En règle générale, le transfert et le transfert d’appels RST entrants à partir d’une passerelle activée pour le routage Location-Based ne sont autorisés que si l’utilisateur cible est activé pour le routage Location-Based et se trouve sur le même site. Sinon, le transfert et le transfert d’appels ne sont pas autorisés. 

Le tableau suivant indique si le transfert d’appel et les transferts d’appel sont autorisés, selon l’emplacement de l’utilisateur cible. Dans cette table, User1, situé dans Site1, déclenche le transfert ou le transfert vers d’autres utilisateurs Teams qui sont également activés pour le routage Location-Based et qui se trouvent à des emplacements différents.  

|Emplacement du point de terminaison de l’utilisateur cible|Un utilisateur1 déclenche un transfert d’appel |Un utilisateur1 déclenche un appel vers l’avant|
|---------|---------|---------|
|Même site réseau que le initiateur (Utilisateur2)|Autorisé|Autorisé|
|Site réseau différent, site activé pour lLocation-Based routage des routages (Utilisateur3)|Non autorisé|Non autorisé|
|Site réseau différent, site non activé pour l'Location-Based routage des utilisateurs (Utilisateur4)|Non autorisé|Non autorisé|
|Réseau interne inconnu (Utilisateur5)| Non autorisé|Non autorisé|
|Réseau externe inconnu (Utilisateur6)| Non autorisé|Non autorisé|

### <a name="teams-user-transfers-or-forwards-call-to-pstn-endpoint"></a>Teams transferts ou transferts d’appel vers le point de terminaison PSTN

#### <a name="user-not-enabled-for-location-based-routing"></a>Utilisateur non activé pour l'Location-Based routage

- Le transfert et le transfert d’un appel PSTN vers un autre numéro PSTN sont autorisés. 
- Le transfert d’un appel VOIP entrant vers le PSTN doit respecter les restrictions de contournement toll de l’appelant. 
    - Si l’appelant n’est pas activé pour le routage Location-Based, il peut être transféré vers n’importe quelle passerelle RST qui n’est pas activée pour le Location-Based routage.
    - Si l’appelant est activé pour le routage Location-Based, il ne peut être transféré qu’vers une passerelle Location-Based routage située sur le même site réseau. 

#### <a name="user-enabled-for-location-based-routing"></a>Utilisateur activé pour l'Location-Based routage

- Le transfert et le transfert d’un appel RSTN vers un autre numéro PSTN doivent être acheminés vers la passerelle Location-Based Routage à partir de celle à partir de celle-ci. 
- Le transfert et le transfert d’un appel VOIP entrant vers le PSTN doivent respecter à la fois l’appelant et les restrictions de contournement toll de l’utilisateur. 
    - Si l’appelant n’est pas activé pour le routage Location-Based, il peut être transféré vers n’importe quelle passerelle RST qui n’est pas activée pour le Location-Based routage.
    - Si l’appelant est activé pour le routage Location-Based, il ne peut être transféré qu’vers une passerelle Location-Based routage située sur le même site réseau.
 
Le tableau suivant montre comment le routage Location-Based affecte le routage d’un appel VOIP à partir de l’utilisateur 1 sur Site1 vers les utilisateurs situés à des emplacements différents qui transfèrent ou transfèrent l’appel vers un point de terminaison PSTN.  

|Utilisateur à l’origine du transfert ou du transfert d’appel  |Transfert vers le PSTN  |Forward to PSTN  |
|---------|---------|---------|
|Même site réseau, site activé pour le routage Location-Based réseau (Utilisateur2)   |Le transfert d’appel peut uniquement être acheminé via Location-Based passerelle 1 activée pour le routage sur Site1, en fonction de la stratégie de routage voix de l’utilisateur2.         |Le routage d’appel peut uniquement être acheminé via Location-Based Passerelle1 activée pour le routage sur Site1, en fonction de la stratégie de routage voix de l’utilisateur2.         |
|Site réseau différent, site activé pour lLocation-Based routage des routages (Utilisateur3)    |Le transfert d’appel ne peut être acheminé que via Location-Based passerelle 1 activée pour le routage sur Site1, en fonction de la stratégie de routage voix de l’utilisateur3.         |Le routage d’appel ne peut être acheminé qu'Location-Based passerelle 1 activée pour le routage sur Site1, en fonction de la stratégie de routage voix de l’utilisateur3.         |
|Site réseau différent, site non activé pour l'Location-Based routage des utilisateurs (Utilisateur4)    |Le transfert d’appel ne peut être acheminé que via Location-Based passerelle 1 activée pour le routage sur Site1, en fonction de la stratégie de routage voix de l’utilisateur4.         |Le routage d’appel peut uniquement être acheminé via Location-Based passerelle 1 activée pour le routage sur Site1, en fonction de la stratégie de routage voix de l’utilisateur4.         |
|Réseau interne inconnu (Utilisateur5)     |Le transfert d’appel ne peut être acheminé que via Location-Based passerelle 1 activée pour le routage sur Site1, en fonction de la stratégie de routage voix de l’utilisateur5.         |Le routage d’appel peut uniquement être acheminé via Location-Based Passerelle1 activée pour le routage sur Site1, en fonction de la stratégie de routage voix de l’utilisateur5.         |
|Réseau externe inconnu (Utilisateur6)   |Le transfert d’appel ne peut être acheminé que via Location-Based Passerelle 1 activée pour le routage sur Site1, en fonction de la stratégie de routage voix de l’utilisateur6.        |Le routage d’appel ne peut être acheminé que via Location-Based passerelle 1 activée pour le routage sur Site1, en fonction de la stratégie de routage voix de l’utilisateur6.         |

### <a name="simultaneous-ringing"></a>Sonnerie simultanée

Lorsqu’un utilisateur activé pour le routage Location-Based reçoit un appel et active la sonnerie simultanée, le routage Location-Based analyse l’emplacement de l’appelant et les points de terminaison des appelés pour déterminer si l’appel doit être acheminé. La sonnerie simultanée suit les mêmes règles Location-Based transferts d’appel et de transfert. 

#### <a name="simultaneous-ringing-for-another-teams-user"></a>Sonnerie simultanée pour un autre Teams utilisateur

Le tableau suivant indique si le Location-Based routage permet d’appeler simultanément plusieurs utilisateurs pour un appel RSTN entrant pour l’utilisateur 1.

|Emplacement du point de terminaison de l’utilisateur cible|Sonnerie simultanée  |
|---------|---------|
|Même site réseau que le initiateur (Utilisateur2)   |Autorisé         |
|Autre site réseau en itinérance activé pour le Location-Based routage (Utilisateur3)   |Non autorisé         |
|Site réseau en itinérance non activé pour Location-Based routage des appels (Utilisateur4)   |Non autorisé        |
|Réseau interne inconnu (Utilisateur5)    | Non autorisé        |
|Réseau externe inconnu (Utilisateur6)    |Non autorisé        |
|L’utilisateur cible est un numéro PSTN    |Les appels ne peuvent être roués que via Location-Based Passerelle1 activée pour le routage sur Site1, en fonction de la stratégie de routage voix de l’utilisateur1.      |

#### <a name="simultaneous-ringing-to-a-pstn-endpoint"></a>Sonnerie simultanée sur un point de terminaison PSTN

Le tableau suivant indique le comportement Location-Based routage pour un appel VOIP entrant à partir de l’utilisateur 1 situé sur Site1 vers des utilisateurs situés à des emplacements différents avec une sonnerie simultanée définie sur un numéro PSTN. 

|Emplacement du point de terminaison utilisateur appelé  |La cible de l’anneau simultané est le point de terminaison PSTN |
|---------|---------|
|Même site réseau, site activé pour le routage Location-Based réseau (Utilisateur2)    |Les appels peuvent uniquement être acheminés via Location-Based passerelle de routage1 sur Site1, en fonction de la stratégie de routage voix de l’utilisateur2.       |
|Autre site réseau activé pour lLocation-Based routage des routages (Utilisateur3)    |Les appels ne peuvent être roués que via Location-Based passerelle de routage1 sur Site1, en fonction de la stratégie de routage vocale de l’utilisateur 3.        |
|Autre site réseau non activé pour le Location-Based routage des utilisateurs (Utilisateur4)    |Les appels ne peuvent être acheminés qu'Location-Based passerelle de routage1 sur Site1, en fonction de la stratégie de routage vocale de l’utilisateur4.         |
|Réseau interne inconnu (Utilisateur5)    |Les appels ne peuvent être acheminés qu'Location-Based passerelle de routage1 sur Site1, en fonction de la stratégie de routage vocale de l’utilisateur5.         |
|Réseau externe inconnu (Utilisateur6)   |Les appels ne peuvent être acheminés qu'Location-Based passerelle de routage1 sur Site1, en fonction de la stratégie de routage vocale de l’utilisateur6.         |

#### <a name="inbound-calls-through-voice-app-auto-attendant-or-call-queue"></a>Appels entrants via l’application vocale (Standard automatique ou file d’attente d’appels)

Les appels RSTN entrants à partir d'Location-Based passerelle activée pour le routage sont autorisés à se connecter à un port automatique ou à une file d’attente d’appels. Les utilisateurs activés pour l'Location-Based ne peuvent recevoir des transferts d’appel entrants de ces applications que s’ils se trouvent sur le même site dont provient l’appel RSTN entrant. 
 
Le transfert d’appel et la sonnerie simultanée vers les utilisateurs et le réseau PSTN sont autorisés pour les transferts d’application vocale. L’exécution de l’appel vers la cible est soumise aux mêmes règles Location-Based routage répertoriées précédemment.  
 
Le forwarding to voicemail is also allowed.  

### <a name="delegation"></a>Délégation

Un Teams utilisateur peut choisir les délégués qui peuvent effectuer et recevoir des appels en leur nom. Les fonctionnalités de délégation Teams sont affectées par le routage Location-Based comme suit : 
- Pour les appels sortants d'Location-Based délégué activé pour le routage au nom d’un délégant, les mêmes règles s’appliquent. Le routage des appels est basé sur la stratégie d’autorisation d’appel du délégué, la stratégie de routage vocal et l’emplacement. Pour plus d’informations, Teams utilisateur place un appel [sortant vers le PSTN.](#teams-user-places-an-outbound-call-to-the-pstn) 
- Pour les appels PSTN entrants à un délégant, les mêmes règles de routage Location-Based qui s’appliquent au routage d’appel ou à la sonnerie simultanée à d’autres utilisateurs s’appliquent également aux délégués. Pour plus d’informations, voir Teams transferts ou transferts d’appel vers un autre utilisateur Teams, transferts ou [](#simultaneous-ringing)transferts d’appel vers le point de terminaison [PSTN](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)et sonnerie simultanée de l’utilisateur [Teams.](#teams-user-transfers-or-forwards-call-to-another-teams-user) Lorsqu’un délégué définit un point de terminaison PSTN comme une cible de sonnerie simultanée, la stratégie de routage vocal du délégué est utilisée pour router l’appel vers le réseau PSTN. 
- Pour la délégation, il est recommandé que le délégant et les délégués associés soient situés sur le même site réseau. 

## <a name="other-planning-considerations"></a>Autres considérations de planification

### <a name="changes-from-an-on-premises-location-based-routing-deployment"></a>Modifications apportées à un déploiement d'Location-Based routage local

La stratégie de routage voix sur le site réseau n’est plus utilisée. À la place, nous utilisons la stratégie de routage voix de l’utilisateur. Cela signifie que pour autoriser les utilisateurs à se déplacer vers d’autres sites, la stratégie de routage voix doit inclure les passerelles des sites en itinérance. 

### <a name="technical-considerations-for-location-based-routing"></a>Considérations techniques relatives au routage géodépendant

Les sous-réseaux IPv4 et IPv6 sont pris en charge, mais IPv6 est prioritaire lors de la vérification d’une correspondance.

### <a name="client-support-for-location-based-routing"></a>Prise en charge client pour Location-Based routage

Les clients de Teams pris en charge sont les suivants :
- Teams clients de bureau (Windows et Mac)
- Teams clients mobiles (iOS et Android)
- Teams Téléphones IP

Le Teams client web et les clients Skype Entreprise web ne sont pas pris en charge.

### <a name="capabilities-not-supported-by-location-based-routing"></a>Fonctionnalités non prises en charge par le routage géodépendant

Location-Based routage ne s’applique pas aux types d’interactions suivants. Location-Based routage n’est pas appliqué lorsque Teams points de terminaison interagissent avec des points de terminaison RSTN dans les scénarios suivants : 
- Parcage d’appel ou récupération des appels via le parcage d’appels 
- Un utilisateur sur site Skype Entreprise un utilisateur Skype Entreprise Online appelle un Teams utilisateur  

### <a name="location-based-routing-for-conferencing"></a>Location-Based routage pour les conférences

Un Location-Based activé pour le routage d’un appel PSTN n’est pas autorisé à démarrer une conférence avec un autre utilisateur ou un numéro PSTN. La connexion aux attendants automatiques ou aux files d’attente d’appels est autorisée. Si l’utilisateur dispose d’une licence de conférence, il doit démarrer une conférence avec les utilisateurs concernés et appeler le RSTN via le pont de conférence pour démarrer une téléconférence.  

### <a name="media-bypass-requirement-for-location-based-routing"></a>Besoin de dérivation média pour Location-Based routage

Si vous déployez un Location-Based en Inde, il est impératif de configurer également la dérivation média. Pour plus d’informations, voir Planifier la dérivation média avec [le routage direct](direct-routing-plan-media-bypass.md) et l’optimisation des médias locaux [pour le routage direct.](direct-routing-media-optimization.md)

### <a name="direct-voice-over-ip-voip"></a>VoIP (Direct Voice over IP)

Direct Voice over IP (VoIP) ne doit être déployé avec aucun équipement téléphonique en Inde.

## <a name="next-steps"></a>Étapes suivantes

Allez à [Configurer les paramètres réseau pour Location-Based routage.](location-based-routing-configure-network-settings.md)

## <a name="related-topics"></a>Voir aussi

- [Activer le routage géodépendant pour le routage direct](location-based-routing-enable.md)
- [Paramètres réseau pour les fonctionnalités vocales cloud dans Teams](cloud-voice-network-settings.md)
