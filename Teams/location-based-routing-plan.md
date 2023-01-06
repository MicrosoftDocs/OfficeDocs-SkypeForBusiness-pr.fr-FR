---
title: Planifier le routage géodépendant pour le routage direct
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: roykuntz
search.appverid: MET150
description: Découvrez comment planifier le routage Location-Based pour le routage direct des téléphones Teams.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 354a3ae6ec4fb482b6ba0d5136597438c37acbe2
ms.sourcegitcommit: eb0e754d7e2877f686021d3ab75b6d8d44db3a95
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/06/2023
ms.locfileid: "69727786"
---
# <a name="plan-location-based-routing-for-direct-routing"></a>Planifier le routage géodépendant pour le routage direct

Dans certains pays et régions, il est illégal de contourner le fournisseur de réseau téléphonique commuté (RTC) pour réduire les coûts des appels longue distance. 

Cet article décrit ce que vous devez savoir pour utiliser Location-Based routage afin de limiter la déviation des péages pour les utilisateurs de Microsoft Teams en fonction de leur emplacement géographique. Cet article s’applique uniquement au routage direct. Location-Based le routage ne s’applique pas au forfait d’appels ou à la connexion d’opérateur.

Lorsque vous êtes prêt à activer le routage Location-Based, consultez :

- [Configurer les paramètres de réseau pour le routage géodépendant](location-based-routing-configure-network-settings.md)
- [Activer le routage géodépendant pour le routage direct](location-based-routing-enable.md)

> [!NOTE]
> Vous ne devez pas utiliser le routage Location-Based pour acheminer dynamiquement les appels RTC en fonction de l’emplacement de l’utilisateur. Cela peut entraîner des résultats inattendus.

## <a name="overview"></a>Vue d’ensemble

Location-Based routage vous permet de restreindre la déviation des péages pour un utilisateur en fonction de la stratégie et de l’emplacement géographique de l’utilisateur au moment d’un appel RTC entrant ou sortant. 

Location-Based routage utilise la topologie de réseau que vous définissez pour la région réseau, le site et le sous-réseau. Lorsque le contournement payant est limité pour un emplacement, vous associez chaque sous-réseau IP et chaque passerelle RTC pour cet emplacement à un site réseau. 

Au moment d’un appel RTC, l’emplacement d’un utilisateur est déterminé par le sous-réseau IP auquel les points de terminaison Teams de l’utilisateur sont connectés. Si un utilisateur a plusieurs clients Teams situés sur différents sites, Location-Based routage applique le routage de chaque client séparément en fonction de l’emplacement des points de terminaison Teams.

Pour plus d’informations sur les paramètres réseau, consultez [Paramètres réseau pour les fonctionnalités vocales cloud dans Teams](cloud-voice-network-settings.md).

Cet article suppose qu’un site réseau peut se trouver dans l’un des états suivants :

- **Activé** : site configuré à l’aide de sous-réseaux et de sites de réseau client et activé pour le routage Location-Based.

- **Non activé** : site configuré à l’aide de sous-réseaux et de sites de réseau client, mais non activé pour le routage Location-Based.

- **Inconnu** : site non configuré à l’aide de sous-réseaux et de sites du réseau client. En règle générale, ces sites sont internes au réseau d’entreprise, mais par conception non configurés, ou externes au réseau d’entreprise. Dans tous les cas, ces sites ne sont pas activés pour le routage Location-Based. 

### <a name="toll-bypass-evaluation-and-outcome"></a>Évaluation et résultat de la déviation des péages

Lorsque Location-Based routage est utilisé, un appel entre un utilisateur Teams et le RTC est évalué pour déterminer si le contournement payant est limité. En fonction des résultats, l’appel se terminera ou ne se terminera pas. 

Si un utilisateur est activé pour le routage Location-Based et qu’il se trouve sur un site où Location-Based restrictions de routage sont appliquées, le contournement payant est limité pour cet utilisateur. Teams utilise les informations suivantes pour déterminer si la déviation des péages est restreinte : 

- Indique si l’utilisateur Teams est activé pour le routage Location-Based tel que défini dans la stratégie d’appel Teams de l’utilisateur.

- Emplacement du site réseau du point de terminaison de l’utilisateur Teams et indique si le site est activé ou non pour Location-Based routage.

- Emplacement du site réseau de la passerelle RTC utilisée par l’appel.

- Indique si la passerelle RTC utilisée par l’appel a été activée pour le routage Location-Based.

- Pour les scénarios de transfert, l’itinéraire de l’appel RTC est basé sur les paramètres de routage de la personne qui transfère l’appel et sur les paramètres de routage Location-Based de l’utilisateur Teams vers lequel l’appel est transféré.  

- Pour les scénarios de conférence et d’appel de groupe, si un utilisateur Teams pour lequel le contournement payant est restreint fait ou a fait partie de l’appel.

Si un appel ne peut pas se terminer, l’utilisateur Teams est averti comme suit :

- Pour les appels RTC sortants, le message suivant s’affiche dans la fenêtre d’appel : Appel non autorisé en raison des paramètres de votre organisation.

- Pour les appels RTC entrants, l’appel est routé en fonction des paramètres de transfert d’appel sans réponse de l’utilisateur Teams appelé, généralement vers la messagerie vocale. Si l’utilisateur Teams n’a pas configuré les paramètres d’appel sans réponse, l’appel se déconnecte.

## <a name="apply-location-based-routing"></a>Appliquer le routage Location-Based

Vous devez appliquer Location-Based routage aux éléments suivants :

- [Utilisateurs](#apply-location-based-routing-at-the-user-location)
- [Sites réseau](#apply-location-based-routing-at-the-network-site)
- [Passerelles RTC](#apply-location-based-routing-at-the-pstn-gateway)

Gardez à l’esprit les meilleures pratiques suivantes :

- La passerelle RTC et le site réseau associés à la passerelle doivent tous deux être activés pour le routage Location-Based.

- Pour passer des appels via une passerelle RTC activée pour le routage Location-Based, les utilisateurs doivent également être activés pour le routage Location-Based.

- Pour permettre aux utilisateurs qui sont activés pour le routage Location-Based de passer des appels RTC sortants à partir d’un site réseau inconnu, les conditions suivantes doivent être remplies :

  - L’appel doit être émis à partir d’une passerelle RTC activée pour le routage Location-Based.
  - La passerelle RTC doit être configurée avec l’indicateur GatewayLbrEnabledUserOverride défini sur True.


### <a name="apply-location-based-routing-at-the-user-location"></a>Appliquer Location-Based routage à l’emplacement de l’utilisateur

La restriction de contournement payant contrôle les conditions dans lesquelles un utilisateur peut effectuer et recevoir des appels RTC et la passerelle RTC qui peut être utilisée. 

Si un utilisateur est soumis à une restriction de contournement payant, cet utilisateur doit être activé pour Location-Based routage. Lorsque l’utilisateur activé se trouve sur un site activé pour le routage Location-Based, l’utilisateur doit effectuer des appels via une passerelle à la fois connectée au site et activée pour le routage Location-Based. 

Location-Based routage fonctionne en déterminant l’emplacement actuel de l’utilisateur en fonction de l’adresse IP du point de terminaison Teams de l’utilisateur et applique les règles en conséquence. L’emplacement d’un utilisateur activé pour Location-Based routage peut être classé comme suit : 

- **L’utilisateur se trouve dans le même Location-Based site activé pour le routage associé à la passerelle RTC où son DID est affecté.**<br>Dans ce scénario, l’utilisateur se trouve dans un site réseau configuré qui est activé pour le routage Location-Based et le numéro de numérotation entrante (DID) de l’utilisateur se termine sur une passerelle RTC qui se trouve sur le même site réseau. Par exemple, l’utilisateur est à son bureau. 

- **L’utilisateur se trouve sur un autre Location-Based site activé pour le routage qui n’est pas associé à la passerelle RTC où son DID est affecté.**<br>Dans ce scénario, l’utilisateur se trouve dans un site réseau configuré qui est activé pour le routage Location-Based, et ce site n’est pas associé à la passerelle RTC où le numéro DID de l’utilisateur est attribué. Par exemple, l’utilisateur se rend dans un autre bureau.  

- **L’utilisateur se trouve sur un site interne qui n’est pas activé pour Location-Based routage.** <br>Dans ce scénario, l’utilisateur se trouve dans un site réseau configuré qui n’est pas activé pour le routage Location-Based. 

- **L’utilisateur se trouve sur un site inconnu.** 
    - L’utilisateur se trouve dans le réseau interne qui n’est pas défini comme un site réseau. 
    - L’utilisateur se trouve en dehors du réseau interne. Par exemple, l’utilisateur est sur Internet à la maison ou dans un café. 

### <a name="apply-location-based-routing-at-the-network-site"></a>Appliquer le routage Location-Based sur le site réseau 

Lorsque les utilisateurs activés pour le routage Location-Based sont itinérants, les sites réseau activés pour Location-Based routage aideront à déterminer les passerelles à utiliser. Par exemple :

- Si un utilisateur activé pour le routage Location-Based est itinérant vers un site activé pour le routage Location-Based, seule la passerelle RTC activée pour le routage Location-Based sur ce site peut être utilisée pour les appels sortants. 

- Si un utilisateur activé pour Location-Based routage est itinérant vers un site qui n’est pas activé pour le routage Location-Based, toute passerelle qui n’est pas activée pour Location-Based routage peut être utilisée pour les appels sortants.  

### <a name="apply-location-based-routing-at-the-pstn-gateway"></a>Appliquer le routage Location-Based à la passerelle RTC  

Pour appliquer le routage Location-Based à la passerelle RTC, vous devez effectuer les opérations suivantes :

- Activez la passerelle pour le routage Location-Based. (Les passerelles doivent être activées pour Location-Based routage afin de s’assurer qu’elles ne peuvent pas être utilisées par les utilisateurs qui ne sont pas activés pour le routage Location-Based.)

- Affectez un site réseau à la passerelle.

Le système détermine ensuite si un utilisateur donné dans un site donné est autorisé à utiliser la passerelle. 

En outre, si vous définissez GatewayLbrEnabledUserOverride sur True, les utilisateurs activés par le routage basé sur l’emplacement dans des sites inconnus, par exemple, les utilisateurs travaillant à domicile peuvent effectuer des appels RTC sortants.


## <a name="restriction-rules"></a>Règles de restriction

Les règles de restriction varient selon qu’un utilisateur Teams est ou non activé pour le routage Location-Based.

### <a name="user-is-enabled-for-location-based-routing"></a>L’utilisateur est activé pour le routage Location-Based

Lorsqu’un utilisateur est activé pour le routage Location-Based, les conditions suivantes s’appliquent :

- **Pour effectuer un appel RTC sortant**, l’une des conditions suivantes doit être vraie :

  - Le point de terminaison de l’utilisateur se trouve sur un site activé pour le routage Location-Based et les appels sont sortants via une passerelle RTC activée pour le routage Location-Based dans le même site.  

  - Le point de terminaison de l’utilisateur se trouve sur un site inconnu et appelle la sortie via une passerelle RTC activée pour le routage Location-Based. La passerelle RTC est configurée avec le paramètre GatewayLbrEnabledUserOverride défini sur True.

  - Le point de terminaison de l’utilisateur se trouve sur un site qui n’est pas activé pour le routage Location-Based et appelle la sortie via une passerelle RTC qui n’est pas activée pour le routage Location-Based.

- **Pour recevoir un appel PSTN entrant**, l’une des conditions suivantes doit être vraie : 

   - Le point de terminaison de réponse de l’utilisateur et la passerelle RTC via laquelle l’entrée d’appel doit se trouver sur le même site que celui activé pour le routage Location-Based. La passerelle RTC doit être activée pour le routage Location-Based.

   - Le point de terminaison de réponse de l’utilisateur et la passerelle RTC via laquelle l’entrée d’appel doit se trouver sur le même site que celui qui n’est pas activé pour le routage Location-Based. La passerelle RTC ne doit pas être activée pour le routage Location-Based.  (Ce scénario implique le réacheminement de l’appel RTC entrant vers l’entrée via une autre passerelle RTC que celle normalement utilisée pour les appels entrants vers le numéro de téléphone de l’utilisateur.)

   - Dans tout autre scénario, par exemple si l’utilisateur est itinérant, l’appel n’est pas autorisé et est routé vers les paramètres de transfert d’appel sans réponse de l’utilisateur (généralement la messagerie vocale).  
   
- **Pour un appel VoIP Teams 1:1 et un transfert vers PSTN**, notez les points suivants :

  - Le routage de l’appel, c’est-à-dire la passerelle RTC à laquelle l’appel est sortant, est basé sur les paramètres de routage de l’utilisateur qui transfère l’appel.

  - La question de savoir si le transfert sera autorisé est basée sur les éléments suivants :
  
    - Le Location-Based paramètres de routage de l’utilisateur transféré vers RTC.
    - Emplacement du site réseau du point de terminaison.
    - Indique si l’emplacement est activé pour Location-Based routage.

    Le transfert est autorisé si l’utilisateur transféré est en mesure d’effectuer cet appel RTC à son emplacement actuel à l’aide de la même passerelle RTC.

- **Pour un appel PSTN entrant ou sortant et un transfert vers un autre utilisateur Teams**, le fait que le transfert soit autorisé dépend des éléments suivants :

   - Paramètres de routage de l’utilisateur qui reçoit l’appel transféré. 
   - Emplacement du site réseau du point de terminaison.
   - Indique si l’emplacement est activé pour Location-Based routage.

   Le transfert est autorisé si la personne recevant l’appel transféré est en mesure d’effectuer ou de recevoir cet appel RTC à son emplacement actuel à l’aide de la passerelle RTC utilisée par l’appel RTC en cours.


### <a name="user-is-not-enabled-for-location-based-routing"></a>L’utilisateur n’est pas activé pour le routage Location-Based

Lorsqu’un utilisateur Teams n’est pas activé pour le routage Location-Based, tous les appels à destination et en provenance de cet utilisateur doivent être acheminés via une passerelle RTC qui n’est pas activée pour le routage Location-Based. Un appel entrant à un tel utilisateur routé via une passerelle RTC activée pour Location-Based routage est acheminé vers les paramètres de transfert d’appel sans réponse de l’utilisateur (généralement la messagerie vocale).

### <a name="decision-flows-for-inbound-and-outbound-calls"></a>Flux de décision pour les appels entrants et sortants

Les diagrammes suivants montrent les flux de décision pour les appels entrants et sortants.

**Appels entrants**

![Diagramme montrant la LBR pour les appels entrants](media/lbr-routing-inbound1.png "Diagramme montrant les scénarios de routage Location-Based")

**Appels sortants**

![Diagramme montrant la LBR pour les appels sortants](media/lbr-routing-outbound1.png "Diagramme montrant les scénarios de routage Location-Based")


## <a name="scenarios-for-location-based-routing"></a>Scénarios de routage géodépendant

Cette section décrit différents scénarios de restriction de la déviation des péages à l’aide du routage Location-Based. Les scénarios comparent la façon dont les appels sont routés pour les utilisateurs qui ne sont pas activés pour le routage Location-Based avec les utilisateurs qui sont activés pour le routage Location-Based.

- [L’utilisateur Teams passe un appel sortant au RTC](#teams-user-places-an-outbound-call-to-the-pstn)
- [L’utilisateur Teams reçoit un appel entrant à partir du RÉSEAU PSTN](#teams-user-receives-an-inbound-call-from-the-pstn)
- [L’utilisateur teams transfère ou transfère un appel à un autre utilisateur Teams](#teams-user-transfers-or-forwards-call-to-another-teams-user)
- [L’utilisateur teams transfère ou transfère l’appel au point de terminaison RTC](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)
- [Sonnerie simultanée](#simultaneous-ringing)
- [Délégation](#delegation)

Le diagramme suivant montre les restrictions activées par Location-Based routage dans chaque scénario. Les utilisateurs, les sites réseau et les passerelles activés pour le routage Location-Based ont une bordure autour d’eux. Utilisez le diagramme comme guide pour vous aider à comprendre le fonctionnement du routage Location-Based dans chaque scénario.  

![Diagramme montrant les scénarios de routage Location-Based.](media/lbr-direct-routing.png "Diagramme montrant les scénarios de routage Location-Based")

### <a name="teams-user-places-an-outbound-call-to-the-pstn"></a>L’utilisateur Teams passe un appel sortant au RTC

#### <a name="user-not-enabled-for-location-based-routing"></a>Utilisateur non activé pour le routage Location-Based

Un utilisateur qui n’est pas activé pour le routage Location-Based peut effectuer des appels sortants à l’aide de n’importe quelle passerelle sur n’importe quel site qui n’est pas activé pour le routage Location-Based via sa stratégie de routage vocal attribuée. Toutefois, si une passerelle est activée pour le routage Location-Based, l’utilisateur ne peut pas effectuer d’appels sortants via la passerelle, même si elle est affectée à sa stratégie de routage vocal. Si l’utilisateur se rend sur un site activé pour le routage Location-Based, il peut uniquement passer des appels via ses passerelles de routage normales qui ne sont pas activées pour le routage Location-Based.
 
#### <a name="user-enabled-for-location-based-routing"></a>Utilisateur activé pour le routage Location-Based

En comparaison, le routage des appels sortants pour les utilisateurs qui sont activés pour Location-Based routage est affecté par l’emplacement réseau du point de terminaison de l’utilisateur. Le tableau suivant montre comment Location-Based routage affecte le routage des appels sortants de User1, en fonction de l’emplacement de User1. 

|Emplacement du point de terminaison Utilisateur1  |Routage des appels sortants pour User1  |
|---------|---------|
|Même site où le DID de l’utilisateur est affecté, site activé pour le routage Location-Based (Site1)      |Appel routé via une passerelle activée pour le routage Location-Based (GW1) sur Site1, en fonction de la stratégie de routage vocal de l’utilisateur         |
|Site différent de celui où le DID de l’utilisateur est attribué, site activé pour le routage Location-Based (Site2)    |Appel routé via une passerelle activée pour le routage Location-Based (GW2) sur site itinérant2, en fonction de la stratégie de routage des voix de l’utilisateur        |
|Site différent de celui où le DID de l’utilisateur est attribué, site non activé pour le routage Location-Based (Site3)  |Appel routé via une passerelle qui n’est pas activé pour Location-Based le routage sur le site qui n’est pas activé pour le routage Location-Based (GW3), en fonction de la stratégie de routage des communications vocales de l’utilisateur       |
|Réseau interne inconnu (Emplacement4)    |  L’appel RTC n’est pas autorisé, sauf si GatewayLbrEnabledUserOverride est défini sur True       |
|Réseau externe inconnu (Emplacement5)    | L’appel RTC n’est pas autorisé, sauf si GatewayLbrEnabledUserOverride est défini sur True       |

### <a name="teams-user-receives-an-inbound-call-from-the-pstn"></a>L’utilisateur Teams reçoit un appel entrant à partir du RÉSEAU PSTN

#### <a name="user-not-enabled-for-location-based-routing"></a>Utilisateur non activé pour le routage Location-Based

Un utilisateur qui n’est pas activé pour le routage Location-Based peut recevoir un appel entrant de la passerelle qui n’est pas activé pour Location-Based routage à partir duquel le numéro DID attribué est entrant. Si l’utilisateur se déplace vers un site qui n’est pas activé pour le routage Location-Based, il peut toujours recevoir des appels via ses passerelles RTC normales.
  
#### <a name="user-enabled-for-location-based-routing"></a>Utilisateur activé pour le routage Location-Based

En comparaison, les utilisateurs activés pour le routage Location-Based peuvent uniquement recevoir des appels entrants à partir de la passerelle RTC à laquelle leur DID est affecté lorsqu’ils se trouvent sur le même site. Le tableau suivant montre comment User1 reçoit les appels entrants lorsque User1 se déplace vers différents emplacements réseau. Si l’appel n’est pas routé vers le point de terminaison de l’utilisateur, il accède aux paramètres de transfert d’appel sans réponse de l’utilisateur, si les paramètres sont configurés. En règle générale, les appels sont transférés vers la messagerie vocale.  

|Emplacement du point de terminaison Utilisateur1  |Routage des appels entrants vers User1  |
|---------|---------|
|Même site que celui où le DID de l’utilisateur est affecté, site activé pour le routage Location-Based (Site1)   | Appels routés vers le point de terminaison de User1 dans Site1        |
|Site différent de celui où le DID de l’utilisateur est attribué, site activé pour le routage Location-Based (Site2)    | Appels non routés vers des points de terminaison dans Site2        |
|Site différent de celui où le DID de l’utilisateur est attribué, site non activé pour le routage Location-Based (Site3)    | Appels non routés vers des points de terminaison dans Site3        |
|Réseau interne inconnu (Emplacement4)   | Appels non routés vers des points de terminaison dans Location4        |
|Réseau externe inconnu (Emplacement5)     | Appels non routés vers des points de terminaison dans Location5        |

### <a name="teams-user-transfers-or-forwards-call-to-another-teams-user"></a>L’utilisateur teams transfère ou transfère un appel à un autre utilisateur Teams

Lorsqu’un point de terminaison RTC est impliqué, Location-Based routage analyse si un utilisateur ou les deux sont activés pour Location-Based routage et détermine si l’appel doit être transféré ou transféré en fonction de l’emplacement des deux points de terminaison. 
 
Le transfert d’appel nécessite que l’utilisateur initialisateur récupère l’appel, tandis que le transfert d’appel ne nécessite pas de réponse à l’appel initial. Les appels peuvent être transférés même si User1 n’est pas à un emplacement pour recevoir des appels entrants (voir le tableau dans [l’utilisateur Teams reçoit un appel entrant de la section RTC](#teams-user-receives-an-inbound-call-from-the-pstn) ) et que les appels ne peuvent pas être transférés si User1 ne peut pas recevoir l’appel entrant. 

#### <a name="user-not-enabled-for-location-based-routing"></a>Utilisateur non activé pour le routage Location-Based

Un utilisateur qui n’est pas activé pour le routage Location-Based peut transférer ou transférer des appels RTC à d’autres utilisateurs qui ne sont pas activés pour le routage Location-Based. Les utilisateurs qui sont activés pour le routage Location-Based se trouvent généralement dans Location-Based passerelles activées pour le routage pour les appels RTC. Par conséquent, les utilisateurs qui ne sont pas activés ne sont pas autorisés à transférer ou à transférer un appel RTC à un utilisateur qui est activé pour Location-Based routage. L’exception est quand un utilisateur Location-Based le routage activé se déplace vers un site qui n’est pas activé pour Location-Based routage. Dans ce scénario, l’appel transféré est autorisé.  

De même, un utilisateur qui n’est pas activé pour le routage Location-Based peut uniquement recevoir un transfert ou un appel RTC transféré d’un autre utilisateur qui n’est pas activé pour le routage Location-Based. 

#### <a name="user-enabled-for-location-based-routing"></a>Utilisateur activé pour le routage Location-Based

Le transfert et le transfert d’appels RTC entrants à partir d’une passerelle activée pour Location-Based le routage n’est autorisé que si l’utilisateur cible est activé pour le routage Location-Based et se trouve sur le même site. Sinon, le transfert et le transfert d’appels ne sont pas autorisés. 

Le tableau suivant indique si le transfert d’appel et les transferts d’appels sont autorisés, en fonction de l’emplacement de l’utilisateur cible. Dans ce tableau, User1, situé dans Site1, lance le transfert ou le transfère à d’autres utilisateurs Teams qui sont également activés pour le routage Location-Based et qui se trouvent à des emplacements différents.  

|Emplacement du point de terminaison de l’utilisateur cible|User1 lance le transfert d’appel |User1 lance le transfert d’appel|
|---------|---------|---------|
|Même site réseau que l’initiateur (Utilisateur2)|Autorisé|Autorisé|
|Site réseau différent, site activé pour le routage Location-Based (Utilisateur3)|Non autorisé|Non autorisé|
|Site réseau différent, site non activé pour le routage Location-Based (Utilisateur4)|Non autorisé|Non autorisé|
|Réseau interne inconnu (Utilisateur5)| Non autorisé|Non autorisé|
|Réseau externe inconnu (Utilisateur6)| Non autorisé|Non autorisé|

### <a name="teams-user-transfers-or-forwards-call-to-pstn-endpoint"></a>L’utilisateur teams transfère ou transfère l’appel au point de terminaison RTC

#### <a name="user-not-enabled-for-location-based-routing"></a>Utilisateur non activé pour le routage Location-Based

- Le transfert et le transfert d’un appel RTC vers un autre numéro RTC sont autorisés. 

- Le transfert et le transfert d’un appel VOIP entrant vers le RTC doivent respecter les restrictions de contournement de péage de l’appelant. 

    - Si l’appelant n’est pas activé pour le routage Location-Based, il peut être transféré vers n’importe quelle passerelle RTC qui n’est pas activée pour le routage Location-Based.
    - Si l’appelant est activé pour le routage Location-Based, il peut uniquement être transféré vers une passerelle activée pour le routage Location-Based située sur le même site réseau. 

#### <a name="user-enabled-for-location-based-routing"></a>Utilisateur activé pour le routage Location-Based

- Le transfert et le transfert entrants d’un appel RTC vers un autre numéro RTC doivent être routés à partir de la même passerelle Location-Based de routage activée que celle sur laquelle l’appel entrant est arrivé.

- Le transfert et le transfert d’un appel VOIP entrant vers le RTC doivent respecter les restrictions de contournement de péage de l’appelant et de l’utilisateur appelé. 

    - Si l’appelant n’est pas activé pour le routage Location-Based, il peut être transféré vers n’importe quelle passerelle RTC qui n’est pas activée pour le routage Location-Based.

    - Si l’appelant est activé pour le routage Location-Based, il ne peut être transféré que vers une passerelle de routage Location-Based située sur le même site réseau.
 
Le tableau suivant montre comment le routage Location-Based affecte le routage d’un appel VOIP à partir de Location-Based routage activé User1 sur Site1 aux utilisateurs de différents emplacements qui transfèrent ou transfèrent l’appel à un point de terminaison RTC.  

|L’utilisateur lance le transfert ou le transfert d’appel  |Transférer ou transférer vers PSTN  |
|---------|---------|
|Même site réseau, site activé pour le routage Location-Based (Utilisateur2)   |L’appel RTC résultant n’est autorisé que si l’itinéraire calculé basé sur la stratégie de routage vocal de User2 aboutit à un itinéraire via Location-Based routage activé Gateway1 sur Site1         |
|Site réseau différent, site activé pour le routage Location-Based (Utilisateur3)    |L’appel RTC résultant n’est autorisé que si l’itinéraire calculé basé sur la stratégie de routage vocal de User3 aboutit à un itinéraire via Location-Based routage activé Gateway1 sur Site1 |
|Site réseau différent, site non activé pour le routage Location-Based (Utilisateur4)    |L’appel RTC résultant n’est autorisé que si l’itinéraire calculé basé sur la stratégie de routage vocal de User4 aboutit à un itinéraire via Location-Based routage activé Gateway1 sur Site1          |
|Réseau interne inconnu (Utilisateur5)     |L’appel RTC résultant n’est autorisé que si l’itinéraire calculé basé sur la stratégie de routage vocal de User5 aboutit à un itinéraire via Location-Based routage activé Gateway1 sur site1          |
|Réseau externe inconnu (Utilisateur6)   |L’appel RTC résultant n’est autorisé que si l’itinéraire calculé basé sur la stratégie de routage vocal de User6 aboutit à un itinéraire via Location-Based routage activé Gateway1 sur Site1          |

### <a name="simultaneous-ringing"></a>Sonnerie simultanée

Lorsqu’un utilisateur activé pour le routage Location-Based reçoit un appel et que la sonnerie simultanée est activée, Location-Based routage analyse l’emplacement de la partie appelante et les points de terminaison des parties appelées pour déterminer si l’appel doit être routé. La sonnerie simultanée suit les mêmes règles de Location-Based que les transferts et les transferts d’appels. 

#### <a name="simultaneous-ringing-for-another-teams-user"></a>Sonnerie simultanée pour un autre utilisateur Teams

Le tableau suivant indique si le routage Location-Based autorise la sonnerie simultanée à différents utilisateurs pour un appel RTC entrant pour User1.

|Emplacement du point de terminaison de l’utilisateur cible|Anneau simultané  |
|---------|---------|
|Même site réseau que l’initiateur (Utilisateur2)   |Autorisé         |
|Différents sites réseau itinérants activés pour le routage Location-Based (Utilisateur3)   |Non autorisé         |
|Site réseau itinérant non activé pour le routage Location-Based (Utilisateur4)   |Non autorisé        |
|Réseau interne inconnu (Utilisateur5)    | Non autorisé        |
|Réseau externe inconnu (Utilisateur6)    |Non autorisé        |
|L’utilisateur cible est un numéro RTC    |L’appel peut uniquement être routé via Location-Based passerelle activée pour le routage1 sur Site1, en fonction de la stratégie de routage vocal de User1      |

#### <a name="simultaneous-ringing-to-a-pstn-endpoint"></a>Sonnerie simultanée à un point de terminaison RTC

Le tableau suivant montre Location-Based comportement de routage pour un appel VoIP entrant à partir de Location-Based routage activé User1 situé sur Site1 aux utilisateurs situés à différents emplacements avec sonnerie simultanée définie sur un numéro RTC. 

|Emplacement du point de terminaison de l’utilisateur appelé  |La cible en anneau simultanée est un point de terminaison PSTN |
|---------|---------|
|Même site réseau, site activé pour le routage Location-Based (Utilisateur2)    |L’appel RTC résultant n’est autorisé que si l’itinéraire calculé basé sur la stratégie de routage vocal de User2 aboutit à un itinéraire via Location-Based routage activé Gateway1 sur Site1        |
|Site réseau différent activé pour le routage Location-Based (Utilisateur3)    |L’appel RTC résultant n’est autorisé que si l’itinéraire calculé basé sur la stratégie de routage vocal de User3 aboutit à un itinéraire via Location-Based routage activé Gateway1 sur Site1         |
|Site réseau différent non activé pour le routage Location-Based (Utilisateur4)    |L’appel RTC résultant n’est autorisé que si l’itinéraire calculé basé sur la stratégie de routage vocal de User4 aboutit à un itinéraire via Location-Based routage activé Gateway1 sur Site1          |
|Réseau interne inconnu (Utilisateur5)    |L’appel RTC résultant n’est autorisé que si l’itinéraire calculé basé sur la stratégie de routage vocal de User5 aboutit à un itinéraire via Location-Based routage activé Gateway1 sur site1          |
|Réseau externe inconnu (Utilisateur6)   |L’appel RTC résultant n’est autorisé que si l’itinéraire calculé basé sur la stratégie de routage vocal de User6 aboutit à un itinéraire via Location-Based routage activé Gateway1 sur Site1          |

#### <a name="inbound-calls-through-voice-apps-auto-attendant-or-call-queue"></a>Appels entrants via des applications vocales (standard automatique ou file d’attente d’appels)

Les appels RTC entrants à partir d’une passerelle Location-Based avec routage sont autorisés à se connecter à un standard automatique ou à une file d’attente d’appels. 

Les utilisateurs activés pour le routage Location-Based sont pris en charge pour recevoir des transferts d’appels entrants pour ces applications lorsqu’ils se trouvent sur le même site d’où provient l’appel RTC entrant. Pour prendre en charge l’optimisation des médias locaux et la déviation du trafic multimédia dans ces scénarios, les files d’attente d’appels doivent être configurées pour le mode de transfert (mode conférence = OFF).
 
Le transfert d’appel et la sonnerie simultanée aux utilisateurs et RTC sont autorisés pour les transferts d’applications vocales. L’exécution de l’appel à la cible est soumise aux mêmes Location-Based règles de routage répertoriées précédemment.  
 
Le transfert vers la messagerie vocale est également autorisé.  

### <a name="delegation"></a>Délégation

Un utilisateur Teams peut choisir des délégués qui peuvent passer et recevoir des appels en leur nom. Les fonctionnalités de délégation dans Teams sont affectées par le routage Location-Based comme suit : 

- Pour les appels sortants à partir d’un délégué Location-Based le routage activé pour le compte d’un délégant, les mêmes règles s’appliquent. Le routage des appels est basé sur la stratégie d’autorisation des appels, la stratégie de routage vocal et l’emplacement du délégué. Pour plus d’informations, consultez [L’utilisateur Teams passe un appel sortant au RTC](#teams-user-places-an-outbound-call-to-the-pstn). 

- Pour les appels RTC entrants vers un délégant, les mêmes règles de routage Location-Based qui s’appliquent au transfert d’appel ou à la sonnerie simultanée à d’autres utilisateurs s’appliquent également aux délégués. Pour plus d’informations, consultez [Transferts d’utilisateurs teams ou transfert d’appel à un autre utilisateur Teams](#teams-user-transfers-or-forwards-call-to-another-teams-user), [Transferts d’utilisateurs Teams ou transfert d’appel vers le point de terminaison RTC](#teams-user-transfers-or-forwards-call-to-pstn-endpoint) et [Sonnerie simultanée](#simultaneous-ringing). Lorsqu’un délégué définit un point de terminaison RTC en tant que cible en anneau simultanée, la stratégie de routage vocal du délégué est utilisée pour acheminer l’appel vers le RTC. 

- Pour la délégation, Microsoft recommande que le délégant et les délégués associés se trouvent dans le même site réseau. 

## <a name="other-planning-considerations"></a>Autres considérations de planification

### <a name="changes-from-an-on-premises-location-based-routing-deployment"></a>Modifications d’un déploiement de routage Location-Based local

La stratégie de routage vocal de site réseau n’est plus utilisée. Au lieu de cela, nous utilisons la stratégie de routage des voix de l’utilisateur. Pour permettre aux utilisateurs d’être itinérants vers d’autres sites, la stratégie de routage vocal doit inclure les passerelles des sites itinérants. 

### <a name="technical-considerations-for-location-based-routing"></a>Considérations techniques relatives au routage géodépendant

Les sous-réseaux IPv4 et IPv6 sont pris en charge. Toutefois, IPv6 est prioritaire lors de la recherche d’une correspondance.

### <a name="client-support-for-location-based-routing"></a>Prise en charge du client pour le routage Location-Based

Les clients Teams suivants sont pris en charge :
- Clients de bureau Teams (Windows et Mac)
- Clients mobiles Teams (iOS et Android)
- Téléphones IP Teams

Le client web Teams et les clients Skype Entreprise ne sont pas pris en charge.

### <a name="capabilities-not-supported-by-location-based-routing"></a>Fonctionnalités non prises en charge par le routage géodépendant

Location-Based le routage ne s’applique pas aux types d’interactions suivants. Location-Based le routage n’est pas appliqué lorsque les points de terminaison Teams interagissent avec les points de terminaison RTC dans les scénarios suivants : 

- Parcage d’appel ou récupération des appels via le parcage d’appels 

- Un utilisateur Skype Entreprise local ou un utilisateur Skype Entreprise Online appelle un utilisateur Teams  

### <a name="location-based-routing-for-conferencing"></a>routage Location-Based pour les conférences

Un utilisateur Location-Based avec routage sans licence d’audioconférence sur un appel RTC n’est pas autorisé à démarrer une conférence avec un autre utilisateur ou numéro RTC. La connexion à des standards automatiques ou des files d’attente d’appels est autorisée.

Si l’utilisateur dispose d’une licence d’audioconférence, il doit démarrer une conférence avec les utilisateurs concernés et appeler le RTC via le pont de conférence pour démarrer une téléconférence. Si l’utilisateur est déjà sur un appel RTC, il peut ajouter un autre utilisateur ou numéro RTC à l’appel en remontant l’appel à l’aide du pont de conférence pour composer un appel.

Dans une téléconférence démarrée par un utilisateur sans licence d’audioconférence, l’ajout de participants RTC n’est pas autorisé s’il y a ou a eu au moins un utilisateur Location-Based le routage activé dans la téléconférence. Si au moins un participant RTC est ou a fait partie d’une telle téléconférence avant qu’un Location-Based participants activés par le routage ait été invité à rejoindre l’appel, ce Location-Based participants activés pour le routage ne peut pas être ajouté à l’appel.

Si l’utilisateur Location-Based le routage activé rejoint la téléconférence à partir d’un site interne qui n’est pas activé pour le routage Location-Based, les restrictions du paragraphe ci-dessus ne sont pas appliquées. 

Les conférences sur réseau pour l’audioconférence ne doivent PAS être déployées avec un équipement de téléphonie en Inde.

Un utilisateur Location-Based avec routage activé sur un appel RTC n’est pas autorisé à fusionner cet appel avec un autre appel. Les éléments suivants ne sont pas pris en charge : enregistrement de l’appel RTC et enregistrement de conformité de l’appel RTC.

### <a name="media-bypass-requirement-for-location-based-routing"></a>Exigence de contournement de média pour le routage Location-Based

Si vous déployez Location-Based routage en Inde, vous devez également configurer la déviation du trafic multimédia. Pour plus d’informations, consultez [Planifier la déviation du trafic multimédia avec le routage direct](direct-routing-plan-media-bypass.md) et [Optimisation des médias locaux pour le routage direct](direct-routing-media-optimization.md).

### <a name="direct-voice-over-ip-voip"></a>Voix directe sur IP (VoIP)

La voix directe sur IP (VoIP) ne doit pas être déployée avec un équipement de téléphonie en Inde.


## <a name="related-articles"></a>Articles connexes

- [Activer le routage géodépendant pour le routage direct](location-based-routing-enable.md)
- [Paramètres réseau pour les fonctionnalités vocales cloud dans Teams](cloud-voice-network-settings.md)
