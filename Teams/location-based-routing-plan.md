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
description: Découvrez comment planifier Location-Based routage pour le routage direct par téléphone Teams.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 795433f832d57767a7937be1a9d3e7f31e73f240
ms.sourcegitcommit: 41a75f1ba5ceb09f8db7d468aa41b63a89ab9c30
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/12/2022
ms.locfileid: "67647438"
---
# <a name="plan-location-based-routing-for-direct-routing"></a>Planifier le routage géodépendant pour le routage direct

Dans certains pays et régions, il est illégal de contourner le fournisseur de réseau téléphonique commuté (RTC) pour réduire les coûts d’appels longue distance. 

Cet article décrit ce que vous devez savoir pour utiliser Location-Based routage afin de limiter le contournement des péages pour les utilisateurs de Microsoft Teams en fonction de leur emplacement géographique. Cet article s’applique uniquement au routage direct. Location-Based le routage ne s’applique pas au plan d’appel ou à l’opérateur Connect.

Lorsque vous êtes prêt à activer Location-Based routage, consultez :

- [Configurer les paramètres de réseau pour le routage géodépendant](location-based-routing-configure-network-settings.md)
- [Déployer les paramètres réseau pour le routage Location-Based](location-based-routing-configure-network-settings.md)
- [Activer le routage géodépendant pour le routage direct](location-based-routing-enable.md)

> [!NOTE]
> Vous ne devez pas utiliser Location-Based routage pour router dynamiquement les appels RTC en fonction de l’emplacement de l’utilisateur. Cela peut entraîner des résultats inattendus.

## <a name="overview"></a>Vue d’ensemble

Location-Based le routage vous permet de limiter le contournement des péages pour un utilisateur en fonction de la stratégie et de l’emplacement géographique de l’utilisateur au moment d’un appel RTC entrant ou sortant. 

Location-Based Routage utilise la topologie de réseau que vous définissez pour la région réseau, le site et le sous-réseau. Lorsque le contournement payant est restreint pour un emplacement, vous associez chaque sous-réseau IP et chaque passerelle RTC pour cet emplacement à un site réseau. 

Au moment d’un appel RTC, l’emplacement d’un utilisateur est déterminé par le sous-réseau IP auquel les points de terminaison Teams de l’utilisateur sont connectés. Si un utilisateur a plusieurs clients Teams situés sur différents sites, Location-Based routage applique le routage de chaque client séparément en fonction de l’emplacement des points de terminaison Teams.

Pour plus d’informations sur les paramètres réseau, consultez [Paramètres réseau pour les fonctionnalités de voix cloud dans Teams](cloud-voice-network-settings.md).

Cet article suppose qu’un site réseau peut se trouver dans l’un des états suivants :

- **Activé** : un site configuré à l’aide de sous-réseaux et de sites réseau locataires et activé pour le routage Location-Based.

- **Non activé** : un site configuré à l’aide de sous-réseaux et de sites réseau locataires, mais non activé pour le routage Location-Based.

- **Inconnu** : site non configuré à l’aide de sous-réseaux et de sites réseau locataires. En règle générale, ces sites sont internes au réseau d’entreprise, mais par conception non configurés, ou externes au réseau d’entreprise. Dans tous les cas, ces sites ne sont pas activés pour le routage Location-Based. 

### <a name="toll-bypass-evaluation-and-outcome"></a>Évaluation et résultat du contournement des péages

Lorsque Location-Based routage est utilisé, un appel entre un utilisateur Teams et le RTC est évalué pour déterminer si le contournement des péages est restreint. Selon les résultats, l’appel se termine ou ne se termine pas. 

Si un utilisateur est activé pour Location-Based routage et que l’utilisateur se trouve sur un site où Location-Based restrictions de routage sont en vigueur, le contournement payant est limité pour cet utilisateur. Teams utilise les informations suivantes pour déterminer si le contournement des péages est restreint : 

- Indique si l’utilisateur Teams est activé pour Location-Based routage tel que défini dans la stratégie d’appel Teams de l’utilisateur.

- Emplacement du site réseau du point de terminaison de l’utilisateur Teams et si le site est activé ou non pour Location-Based routage.

- Emplacement du site réseau de la passerelle RTC utilisée par l’appel.

- Indique si la passerelle RTC utilisée par l’appel a été activée pour Location-Based routage.

- Pour les scénarios de transfert, l’itinéraire de l’appel RTC est basé sur les paramètres de routage de la personne qui transfère l’appel et sur les paramètres de routage Location-Based de l’utilisateur Teams vers lequel l’appel est transféré.  

- Pour les scénarios de conférence et d’appel de groupe, si un utilisateur Teams pour lequel le contournement payant est restreint fait ou a fait partie de l’appel.

Si un appel ne peut pas se terminer, l’utilisateur Teams est averti comme suit :

- Pour les appels RTC sortants, le message suivant s’affiche dans la fenêtre d’appel : l’appel n’est pas autorisé en raison des paramètres de votre organisation.

- Pour les appels RTC entrants, l’appel est routé en fonction des paramètres de transfert d’appel sans réponse de l’utilisateur Teams, généralement vers la messagerie vocale. Si les paramètres d’appel sans réponse ne sont pas configurés pour l’utilisateur Teams, l’appel se déconnecte.

## <a name="apply-location-based-routing"></a>Appliquer Location-Based routage

Vous devez appliquer Location-Based routage aux éléments suivants :

- [Utilisateurs](#apply-location-based-routing-at-the-user-location)
- [Sites réseau](#apply-location-based-routing-at-the-network-site)
- [Passerelles RTC](#apply-location-based-routing-at-the-pstn-gateway)

Gardez à l’esprit les meilleures pratiques suivantes :

- La passerelle RTC et le site réseau associés à la passerelle doivent tous deux être activés pour Location-Based routage.

- Pour passer des appels via une passerelle RTC activée pour le routage Location-Based, les utilisateurs doivent également être activés pour Location-Based routage.

- Pour permettre aux utilisateurs qui sont activés pour Location-Based routage de passer des appels RTC sortants à partir d’un site réseau inconnu, les éléments suivants doivent être vrais :

  - L’appel doit se dégresser à partir d’une passerelle RTC activée pour le routage Location-Based.
  - La passerelle PSTN doit être configurée avec l’indicateur GatewayLbrEnabledUserOverride défini sur True.


### <a name="apply-location-based-routing-at-the-user-location"></a>Appliquer Location-Based routage à l’emplacement de l’utilisateur

La restriction de contournement payant contrôle les conditions dans lesquelles un utilisateur peut effectuer et recevoir des appels RTC et la passerelle RTC qui peut être utilisée. 

Si un utilisateur est soumis à une restriction de contournement de péage, il doit être activé pour Location-Based routage. Lorsque l’utilisateur activé se trouve sur un site activé pour le routage Location-Based, l’utilisateur doit passer des appels via une passerelle qui est à la fois connectée au site et activée pour Location-Based routage. 

Location-Based routage fonctionne en déterminant l’emplacement actuel de l’utilisateur en fonction de l’adresse IP du point de terminaison Teams de l’utilisateur et applique les règles en conséquence. L’emplacement d’un utilisateur qui est activé pour Location-Based routage peut être classé comme suit : 

- **L’utilisateur se trouve sur le même Location-Based site activé pour le routage associé à la passerelle RTC où son DID est affecté.**<br>Dans ce scénario, l’utilisateur se trouve dans un site réseau configuré qui est activé pour le routage Location-Based et le numéro de numérotation directe entrante (DID) de l’utilisateur se termine sur une passerelle RTC qui se trouve dans le même site réseau. Par exemple, l’utilisateur est à son bureau. 

- **L’utilisateur se trouve dans un autre Location-Based site activé pour le routage qui n’est pas associé à la passerelle RTC où son DID est affecté.**<br>Dans ce scénario, l’utilisateur se trouve dans un site réseau configuré qui est activé pour le routage Location-Based, et ce site n’est pas associé à la passerelle RTC où le numéro DID de l’utilisateur est affecté. Par exemple, l’utilisateur se déplace vers un autre bureau.  

- **L’utilisateur se trouve sur un site interne qui n’est pas activé pour le routage Location-Based.** <br>Dans ce scénario, l’utilisateur se trouve dans un site réseau configuré qui n’est pas activé pour le routage Location-Based. 

- **L’utilisateur se trouve sur un site inconnu.** 
    - L’utilisateur se trouve dans le réseau interne qui n’est pas défini comme un site réseau. 
    - L’utilisateur se trouve en dehors du réseau interne. Par exemple, l’utilisateur est sur Internet à la maison ou dans un café. 

### <a name="apply-location-based-routing-at-the-network-site"></a>Appliquer Location-Based routage sur le site réseau 

Lorsque les utilisateurs qui sont activés pour Location-Based routage sont itinérants, les sites réseau activés pour le routage Location-Based vous aideront à déterminer les passerelles à utiliser. Par exemple :

- Si un utilisateur activé pour Location-Based Routage se déplace vers un site activé pour le routage Location-Based, seule la passerelle RTC activée pour le routage Location-Based sur ce site peut être utilisée pour les appels sortants. 

- Si un utilisateur qui est activé pour Location-Based routage se déplace vers un site qui n’est pas activé pour le routage Location-Based, toute passerelle qui n’est pas activée pour le routage Location-Based peut être utilisée pour les appels sortants.  

### <a name="apply-location-based-routing-at-the-pstn-gateway"></a>Appliquer Location-Based routage sur la passerelle RTC  

Pour appliquer Location-Based routage sur la passerelle RTC, vous devez effectuer les opérations suivantes :

- Activez la passerelle pour Location-Based routage. (Les passerelles doivent être activées pour Location-Based routage afin de s’assurer qu’elles ne peuvent pas être utilisées par les utilisateurs qui ne sont pas activés pour le routage Location-Based.)

- Affectez un site réseau à la passerelle.

Le système détermine ensuite si un utilisateur donné dans un site donné est autorisé à utiliser la passerelle. 

En outre, si vous définissez GatewayLbrEnabledUserOverride sur True, Location-Based-Routing enabled users in unknown sites (par exemple, utilisateurs travaillant à la maison) peut effectuer des appels RTC sortants.


## <a name="restriction-rules"></a>Règles de restriction

Les règles de restriction varient selon qu’un utilisateur Teams est ou non activé pour Location-Based routage.

### <a name="user-is-enabled-for-location-based-routing"></a>L’utilisateur est activé pour le routage Location-Based

Lorsqu’un utilisateur est activé pour Location-Based routage, les éléments suivants s’appliquent :

- **Pour effectuer un appel RTC sortant**, l’un des éléments suivants doit être vrai :

  - Le point de terminaison de l’utilisateur se trouve sur un site activé pour le routage Location-Based et appelle la sortie via une passerelle RTC activée pour le routage Location-Based dans le même site.  

  - Le point de terminaison de l’utilisateur se trouve sur un site inconnu et appelle la sortie via une passerelle RTC activée pour le routage Location-Based. La passerelle RTC est configurée avec le paramètre GatewayLbrEnabledUserOverride défini sur True.

  - Le point de terminaison de l’utilisateur se trouve sur un site qui n’est pas activé pour le routage Location-Based et appelle la sortie via une passerelle RTC qui n’est pas activée pour le routage Location-Based.

- **Pour recevoir un appel RTC entrant**, l’un des éléments suivants doit être vrai : 

   - Le point de terminaison de réponse de l’utilisateur et la passerelle RTC par laquelle l’entrée d’appel doit se trouver sur le même site que celui activé pour Location-Based routage. La passerelle RTC doit être activée pour Location-Based routage.

   - Le point de terminaison de réponse de l’utilisateur et la passerelle RTC par laquelle l’entrée d’appel doit se trouver sur le même site que celui qui n’est pas activé pour le routage Location-Based. La passerelle RTC ne doit pas être activée pour le routage Location-Based.  (Ce scénario implique le réacheminement de l’appel RTC entrant vers l’entrée via une autre passerelle RTC que celle normalement utilisée pour les appels entrants vers le numéro de téléphone de l’utilisateur.)

   - Dans tout autre scénario, par exemple si l’utilisateur est itinérant, l’appel n’est pas autorisé et est routée vers les paramètres de transfert d’appel sans réponse de l’utilisateur (généralement la messagerie vocale).  
   
- **Pour un appel VoIP Teams 1:1 et un transfert vers PSTN**, notez les points suivants :

  - Le routage de l’appel, c’est-à-dire la passerelle RTC vers la sortie de l’appel, est basé sur les paramètres de routage de l’utilisateur qui transfère l’appel.

  - La question de savoir si le transfert sera autorisé est basée sur les éléments suivants :
  
    - Le Location-Based paramètres de routage de l’utilisateur transféré vers PSTN.
    - Emplacement du site réseau du point de terminaison.
    - Indique si l’emplacement est activé pour le routage Location-Based.

    Le transfert est autorisé si l’utilisateur transféré est en mesure d’effectuer cet appel RTC à son emplacement actuel à l’aide de la même passerelle RTC.

- **Pour un appel RTC entrant ou sortant et un transfert vers un autre utilisateur Teams**, l’autorisation du transfert dépend des éléments suivants :

   - Paramètres de routage de l’utilisateur qui reçoit l’appel transféré. 
   - Emplacement du site réseau du point de terminaison.
   - Indique si l’emplacement est activé pour le routage Location-Based.

   Le transfert est autorisé si la personne qui reçoit l’appel transféré est en mesure d’effectuer ou de recevoir cet appel RTC à son emplacement actuel à l’aide de la passerelle RTC utilisée par l’appel RTC en cours.


### <a name="user-is-not-enabled-for-location-based-routing"></a>L’utilisateur n’est pas activé pour le routage Location-Based

Lorsqu’un utilisateur Teams n’est pas activé pour le routage Location-Based, tous les appels vers et depuis cet utilisateur doivent être acheminés via une passerelle RTC qui n’est pas activée pour le routage Location-Based. Un appel entrant à un tel utilisateur routé via une passerelle RTC activée pour le routage Location-Based est acheminé vers les paramètres de transfert d’appel sans réponse de l’utilisateur (généralement la messagerie vocale).

### <a name="decision-flows-for-inbound-and-outbound-calls"></a>Flux de décision pour les appels entrants et sortants

Les diagrammes suivants montrent les flux de décision pour les appels entrants et sortants.

**Appels entrants**

![Diagramme montrant LBR pour les appels entrants](media/lbr-routing-inbound1.png "Diagramme montrant les scénarios de routage Location-Based")

**Appels sortants**

![Diagramme montrant LBR pour les appels sortants](media/lbr-routing-outbound1.png "Diagramme montrant les scénarios de routage Location-Based")


## <a name="scenarios-for-location-based-routing"></a>Scénarios de routage géodépendant

Cette section décrit différents scénarios de restriction du contournement des péages à l’aide du routage Location-Based. Les scénarios comparent la façon dont les appels sont routées pour les utilisateurs qui ne sont pas activés pour le routage Location-Based avec les utilisateurs qui sont activés pour le routage Location-Based.

- [L’utilisateur Teams passe un appel sortant au RTC](#teams-user-places-an-outbound-call-to-the-pstn)
- [L’utilisateur Teams reçoit un appel entrant du RTC](#teams-user-receives-an-inbound-call-from-the-pstn)
- [L’utilisateur Teams transfère ou transfère l’appel à un autre utilisateur Teams](#teams-user-transfers-or-forwards-call-to-another-teams-user)
- [L’utilisateur Teams transfère ou transfère l’appel au point de terminaison RTC](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)
- [Sonnerie simultanée](#simultaneous-ringing)
- [Délégation](#delegation)

Le diagramme suivant montre les restrictions activées par Location-Based routage dans chaque scénario. Les utilisateurs, les sites réseau et les passerelles activés pour Location-Based routage ont une bordure autour d’eux. Utilisez le diagramme comme guide pour vous aider à comprendre le fonctionnement du routage Location-Based dans chaque scénario.  

![Diagramme montrant les scénarios de routage Location-Based.](media/lbr-direct-routing.png "Diagramme montrant les scénarios de routage Location-Based")

### <a name="teams-user-places-an-outbound-call-to-the-pstn"></a>L’utilisateur Teams passe un appel sortant au RTC

#### <a name="user-not-enabled-for-location-based-routing"></a>Utilisateur non activé pour le routage Location-Based

Un utilisateur qui n’est pas activé pour le routage Location-Based peut effectuer des appels sortants à l’aide d’une passerelle sur n’importe quel site qui n’est pas activé pour Location-Based routage via sa stratégie de routage vocal affectée. Toutefois, si une passerelle est activée pour Location-Based routage, l’utilisateur ne peut pas effectuer d’appels sortants via la passerelle, même si elle est affectée à sa stratégie de routage vocal. Si l’utilisateur se déplace vers un site activé pour le routage Location-Based, il peut uniquement effectuer des appels par le biais de ses passerelles de routage normales qui ne sont pas activées pour le routage Location-Based.
 
#### <a name="user-enabled-for-location-based-routing"></a>Utilisateur activé pour le routage Location-Based

En comparaison, le routage des appels sortants pour les utilisateurs qui sont activés pour Location-Based routage est affecté par l’emplacement réseau du point de terminaison de l’utilisateur. Le tableau suivant montre comment Location-Based routage affecte le routage des appels sortants d’User1, en fonction de l’emplacement de User1. 

|Emplacement du point de terminaison User1  |Routage des appels sortants pour User1  |
|---------|---------|
|Même site où l’instruction DID de l’utilisateur est affectée, site activé pour le routage Location-Based (Site1)      |Appel routée via la passerelle activée pour le routage Location-Based (GW1) sur Site1, en fonction de la stratégie de routage vocal de l’utilisateur         |
|Site différent de celui où le DID de l’utilisateur est affecté, site activé pour le routage Location-Based (Site2)    |Appel routée via la passerelle activée pour le routage Location-Based (GW2) sur roam Site2, en fonction de la stratégie de routage vocal de l’utilisateur        |
|Site différent de celui où le DID de l’utilisateur est affecté, site non activé pour le routage Location-Based (Site3)  |Appel routée via une passerelle qui n’est pas activée pour le routage Location-Based sur le site qui n’est pas activé pour le routage Location-Based (GW3), en fonction de la stratégie de routage vocal de l’utilisateur       |
|Réseau interne inconnu (Location4)    |  Appel RTC non autorisé, sauf si gatewayLbrEnabledUserOverride est défini sur True       |
|Réseau externe inconnu (Location5)    | Appel RTC non autorisé, sauf si gatewayLbrEnabledUserOverride est défini sur True       |

### <a name="teams-user-receives-an-inbound-call-from-the-pstn"></a>L’utilisateur Teams reçoit un appel entrant du RTC

#### <a name="user-not-enabled-for-location-based-routing"></a>Utilisateur non activé pour le routage Location-Based

Un utilisateur qui n’est pas activé pour Location-Based Routage peut recevoir un appel entrant de la passerelle qui n’est pas activé pour Location-Based routage à partir duquel son numéro DID attribué est attribué. Si l’utilisateur se déplace vers un site qui n’est pas activé pour Location-Based routage, il peut toujours recevoir des appels via ses passerelles RTC normales.
  
#### <a name="user-enabled-for-location-based-routing"></a>Utilisateur activé pour le routage Location-Based

En comparaison, les utilisateurs activés pour le routage Location-Based ne peuvent recevoir des appels entrants que de la passerelle RTC à laquelle leur DID est affecté lorsqu’ils se trouvent sur le même site. Le tableau suivant montre comment User1 reçoit les appels entrants quand User1 se déplace vers différents emplacements réseau. Si l’appel n’est pas routée vers le point de terminaison de l’utilisateur, il accède aux paramètres de transfert d’appel sans réponse de l’utilisateur, si les paramètres sont configurés. En règle générale, les appels sont transférés à la messagerie vocale.  

|Emplacement du point de terminaison User1  |Routage des appels entrants vers User1  |
|---------|---------|
|Même site que celui où le DID de l’utilisateur est affecté, site activé pour le routage Location-Based (Site1)   | Appels routées vers le point de terminaison User1 dans Site1        |
|Site différent de celui où le DID de l’utilisateur est affecté, site activé pour le routage Location-Based (Site2)    | Appels non routées vers des points de terminaison dans Site2        |
|Site différent de celui où le DID de l’utilisateur est affecté, site non activé pour le routage Location-Based (Site3)    | Appels non routées vers des points de terminaison dans Site3        |
|Réseau interne inconnu (Location4)   | Appels non routées vers des points de terminaison dans Location4        |
|Réseau externe inconnu (Location5)     | Appels non routées vers des points de terminaison dans Location5        |

### <a name="teams-user-transfers-or-forwards-call-to-another-teams-user"></a>L’utilisateur Teams transfère ou transfère l’appel à un autre utilisateur Teams

Lorsqu’un point de terminaison RTC est impliqué, Location-Based routage analyse si un ou les deux utilisateurs sont activés pour le routage Location-Based et détermine si l’appel doit être transféré ou transféré en fonction de l’emplacement des deux points de terminaison. 
 
Le transfert d’appel nécessite que l’utilisateur initial récupère l’appel alors que le transfert d’appel ne nécessite pas la réponse de l’appel initial. Les appels peuvent être transférés même si User1 n’est pas à un emplacement pour recevoir des appels entrants (voir le tableau dans [l’utilisateur Teams reçoit un appel entrant à partir de la section RTC](#teams-user-receives-an-inbound-call-from-the-pstn) ) et que les appels ne peuvent pas être transférés si User1 ne peut pas recevoir l’appel entrant. 

#### <a name="user-not-enabled-for-location-based-routing"></a>Utilisateur non activé pour le routage Location-Based

Un utilisateur qui n’est pas activé pour Location-Based routage peut transférer ou transférer des appels RTC à d’autres utilisateurs qui ne sont pas activés pour Location-Based routage. Les utilisateurs qui sont activés pour le routage Location-Based sont généralement colocalisations sur Location-Based passerelles activées pour le routage pour les appels RTC. Par conséquent, les utilisateurs qui ne sont pas activés ne sont pas autorisés à transférer un appel RTC à un utilisateur qui est activé pour Location-Based routage. L’exception est quand un utilisateur Location-Based routage activé se déplace vers un site qui n’est pas activé pour le routage Location-Based. Dans ce scénario, l’appel transféré est autorisé.  

De même, un utilisateur qui n’est pas activé pour Location-Based Routage ne peut recevoir qu’un appel PSTN transféré ou transféré d’un autre utilisateur qui n’est pas activé pour le routage Location-Based. 

#### <a name="user-enabled-for-location-based-routing"></a>Utilisateur activé pour le routage Location-Based

Le transfert et le transfert d’appels RTC entrants à partir d’une passerelle activée pour le routage Location-Based sont autorisés uniquement si l’utilisateur cible est activé pour le routage Location-Based et se trouve sur le même site. Sinon, le transfert et le transfert d’appels ne sont pas autorisés. 

Le tableau suivant indique si le transfert d’appel et les transferts d’appels sont autorisés, en fonction de l’emplacement de l’utilisateur cible. Dans ce tableau, User1, situé dans Site1, lance le transfert ou le transfert à d’autres utilisateurs Teams qui sont également activés pour le routage Location-Based et qui se trouvent dans différents emplacements.  

|Emplacement du point de terminaison utilisateur cible|User1 lance le transfert d’appels |User1 lance l’appel vers l’avant|
|---------|---------|---------|
|Même site réseau que l’initiateur (User2)|Autorisé|Autorisé|
|Site réseau différent, site activé pour le routage Location-Based (User3)|Non autorisé|Non autorisé|
|Site réseau différent, site non activé pour le routage Location-Based (User4)|Non autorisé|Non autorisé|
|Réseau interne inconnu (User5)| Non autorisé|Non autorisé|
|Réseau externe inconnu (User6)| Non autorisé|Non autorisé|

### <a name="teams-user-transfers-or-forwards-call-to-pstn-endpoint"></a>L’utilisateur Teams transfère ou transfère l’appel au point de terminaison RTC

#### <a name="user-not-enabled-for-location-based-routing"></a>Utilisateur non activé pour le routage Location-Based

- Le transfert et le transfert d’un appel RTC vers un autre numéro RTC sont autorisés. 

- Le transfert et le transfert d’un appel VOIP entrant au rtc doivent respecter les restrictions de contournement de péage de l’appelant. 

    - Si l’appelant n’est pas activé pour Location-Based routage, il peut être transféré vers une passerelle RTC qui n’est pas activée pour Location-Based routage.
    - Si l’appelant est activé pour Location-Based routage, il ne peut être transféré qu’à une passerelle Location-Based routage située sur le même site réseau. 

#### <a name="user-enabled-for-location-based-routing"></a>Utilisateur activé pour le routage Location-Based

- Le transfert et le transfert entrants d’un appel RTC vers un autre numéro RTC doivent être acheminés vers la même passerelle Location-Based la passerelle activée pour le routage sur laquelle l’appel entrant est arrivé.

- Le transfert et le transfert d’un appel VOIP entrant au RTC doivent respecter à la fois l’appelant et les restrictions de contournement de péage de l’utilisateur. 

    - Si l’appelant n’est pas activé pour Location-Based routage, il peut être transféré vers une passerelle RTC qui n’est pas activée pour Location-Based routage.

    - Si l’appelant est activé pour Location-Based routage, il ne peut être transféré qu’à une passerelle activée pour le routage Location-Based située sur le même site réseau.
 
Le tableau suivant montre comment Location-Based routage affecte le routage d’un appel VOIP à partir de Location-Based Le routage activé user1 sur Site1 aux utilisateurs situés à différents emplacements qui transfèrent ou transfèrent l’appel à un point de terminaison RTC.  

|L’utilisateur lance un transfert d’appel ou un transfert  |Transfert ou transfert vers PSTN  |
|---------|---------|
|Même site réseau, site activé pour le routage Location-Based (User2)   |L’appel RTC résultant n’est autorisé que si l’itinéraire calculé basé sur la stratégie de routage vocal d’User2 aboutit à un itinéraire via Location-Based passerelle 1 activée pour le routage sur Site1         |
|Site réseau différent, site activé pour le routage Location-Based (User3)    |L’appel RTC résultant n’est autorisé que si l’itinéraire calculé basé sur la stratégie de routage vocal d’User3 aboutit à un itinéraire via Location-Based passerelle 1 activée pour le routage sur Site1 |
|Site réseau différent, site non activé pour le routage Location-Based (User4)    |L’appel RTC résultant n’est autorisé que si l’itinéraire calculé basé sur la stratégie de routage vocal user4 aboutit à un itinéraire via Location-Based passerelle 1 activée pour le routage sur Site1          |
|Réseau interne inconnu (User5)     |L’appel RTC résultant n’est autorisé que si l’itinéraire calculé basé sur la stratégie de routage vocal user5 aboutit à un itinéraire via Location-Based passerelle 1 activée pour le routage sur Site1          |
|Réseau externe inconnu (User6)   |L’appel RTC résultant n’est autorisé que si l’itinéraire calculé basé sur la stratégie de routage vocal user6 aboutit à un itinéraire via Location-Based passerelle 1 activée pour le routage sur Site1          |

### <a name="simultaneous-ringing"></a>Sonnerie simultanée

Lorsqu’un utilisateur activé pour Location-Based Routage reçoit un appel et que la sonnerie simultanée est activée, Location-Based routage analyse l’emplacement de la partie appelante et les points de terminaison des parties appelées pour déterminer si l’appel doit être routée. La sonnerie simultanée suit les mêmes règles Location-Based que les transferts et transferts d’appel. 

#### <a name="simultaneous-ringing-for-another-teams-user"></a>Sonnerie simultanée pour un autre utilisateur Teams

Le tableau suivant indique si Location-Based routage autorise la sonnerie simultanée à différents utilisateurs pour un appel RTC entrant pour User1.

|Emplacement du point de terminaison utilisateur cible|Sonnerie simultanée  |
|---------|---------|
|Même site réseau que l’initiateur (User2)   |Autorisé         |
|Différents sites réseau itinérants activés pour le routage Location-Based (User3)   |Non autorisé         |
|Site réseau itinérant non activé pour le routage Location-Based (User4)   |Non autorisé        |
|Réseau interne inconnu (User5)    | Non autorisé        |
|Réseau externe inconnu (User6)    |Non autorisé        |
|L’utilisateur cible est un numéro RTC    |L’appel peut uniquement être routée via Location-Based passerelle 1 activée pour le routage sur Site1, en fonction de la stratégie de routage vocal d’User1      |

#### <a name="simultaneous-ringing-to-a-pstn-endpoint"></a>Sonnerie simultanée vers un point de terminaison RTC

Le tableau suivant montre Location-Based comportement de routage pour un appel VoIP entrant à partir de Location-Based Utilisateur1 activé pour le routage situé sur Site1 aux utilisateurs situés à différents emplacements avec un anneau simultané défini sur un numéro RTC. 

|Emplacement du point de terminaison utilisateur appelé  |La cible d’anneau simultanée est un point de terminaison PSTN |
|---------|---------|
|Même site réseau, site activé pour le routage Location-Based (User2)    |L’appel RTC résultant n’est autorisé que si l’itinéraire calculé basé sur la stratégie de routage vocal d’User2 aboutit à un itinéraire via Location-Based passerelle 1 activée pour le routage sur Site1        |
|Site réseau différent activé pour le routage Location-Based (User3)    |L’appel RTC résultant n’est autorisé que si l’itinéraire calculé basé sur la stratégie de routage vocal d’User3 aboutit à un itinéraire via Location-Based passerelle 1 activée pour le routage sur Site1         |
|Autre site réseau non activé pour le routage Location-Based (User4)    |L’appel RTC résultant n’est autorisé que si l’itinéraire calculé basé sur la stratégie de routage vocal user4 aboutit à un itinéraire via Location-Based passerelle 1 activée pour le routage sur Site1          |
|Réseau interne inconnu (User5)    |L’appel RTC résultant n’est autorisé que si l’itinéraire calculé basé sur la stratégie de routage vocal user5 aboutit à un itinéraire via Location-Based passerelle 1 activée pour le routage sur Site1          |
|Réseau externe inconnu (User6)   |L’appel RTC résultant n’est autorisé que si l’itinéraire calculé basé sur la stratégie de routage vocal user6 aboutit à un itinéraire via Location-Based passerelle 1 activée pour le routage sur Site1          |

#### <a name="inbound-calls-through-voice-apps-auto-attendant-or-call-queue"></a>Appels entrants via des applications vocales (standard automatique ou file d’attente d’appels)

Les appels RTC entrants à partir d’une passerelle activée pour le routage Location-Based sont autorisés à se connecter à un standard automatique ou à une file d’attente d’appels. 

Les utilisateurs activés pour Location-Based routage sont pris en charge pour recevoir des transferts d’appels entrants pour ces applications lorsqu’ils se trouvent sur le même site que celui d’où provient l’appel RTC entrant.
 
Le transfert d’appel et la sonnerie simultanée aux utilisateurs et au rtc sont autorisés pour les transferts d’applications vocales. L’exécution de l’appel à la cible est soumise aux mêmes règles de routage Location-Based répertoriées précédemment.  
 
Le transfert vers la messagerie vocale est également autorisé.  

### <a name="delegation"></a>Délégation

Un utilisateur Teams peut choisir des délégués qui peuvent passer et recevoir des appels en leur nom. Les fonctionnalités de délégation dans Teams sont affectées par Location-Based routage comme suit : 

- Pour les appels sortants à partir d’un délégué Location-Based de routage activé pour le compte d’un délégant, les mêmes règles s’appliquent. Le routage des appels est basé sur la stratégie d’autorisation des appels, la stratégie de routage vocal et l’emplacement du délégué. Pour plus d’informations, consultez [l’utilisateur Teams qui place un appel sortant au RTC](#teams-user-places-an-outbound-call-to-the-pstn). 

- Pour les appels RTC entrants à un délégant, les mêmes règles de routage Location-Based qui s’appliquent au transfert d’appel ou à la sonnerie simultanée à d’autres utilisateurs s’appliquent également aux délégués. Pour plus d’informations, consultez [transferts d’utilisateurs Teams ou transferts d’appel à un autre utilisateur Teams](#teams-user-transfers-or-forwards-call-to-another-teams-user), [transferts d’utilisateurs Teams ou transferts d’appel vers le point](#teams-user-transfers-or-forwards-call-to-pstn-endpoint) de terminaison RTC et [sonnerie simultanée](#simultaneous-ringing). Lorsqu’un délégué définit un point de terminaison RTC comme cible d’anneau simultanée, la stratégie de routage vocal du délégué est utilisée pour router l’appel vers le rtc. 

- Pour la délégation, Microsoft recommande que le délégeur et les délégués associés se trouvent dans le même site réseau. 

## <a name="other-planning-considerations"></a>Autres considérations de planification

### <a name="changes-from-an-on-premises-location-based-routing-deployment"></a>Modifications d’un déploiement local de routage Location-Based

La stratégie de routage vocal de site réseau n’est plus utilisée. Au lieu de cela, nous utilisons la stratégie de routage vocal de l’utilisateur. Pour permettre aux utilisateurs de se déplacer vers d’autres sites, la stratégie de routage vocal doit inclure les passerelles des sites itinérants. 

### <a name="technical-considerations-for-location-based-routing"></a>Considérations techniques relatives au routage géodépendant

Les sous-réseaux IPv4 et IPv6 sont pris en charge. Toutefois, IPv6 est prioritaire lors de la vérification d’une correspondance.

### <a name="client-support-for-location-based-routing"></a>Prise en charge du client pour le routage Location-Based

Les clients Teams suivants sont pris en charge :
- Clients de bureau Teams (Windows et Mac)
- Clients mobiles Teams (iOS et Android)
- Téléphones IP Teams

Le client web Teams et les clients Skype Entreprise ne sont pas pris en charge.

### <a name="capabilities-not-supported-by-location-based-routing"></a>Fonctionnalités non prises en charge par le routage géodépendant

Location-Based routage ne s’applique pas aux types d’interactions suivants. Location-Based le routage n’est pas appliqué lorsque les points de terminaison Teams interagissent avec des points de terminaison RTC dans les scénarios suivants : 

- Parcage d’appel ou récupération des appels via le parcage d’appels 

- Un utilisateur Skype Entreprise local ou un utilisateur Skype Entreprise Online appelle un utilisateur Teams  

### <a name="location-based-routing-for-conferencing"></a>Location-Based routage pour les conférences

Un utilisateur Location-Based routage activé sans licence d’audioconférence sur un appel RTC n’est pas autorisé à démarrer une conférence avec un autre utilisateur ou un numéro RTC. La connexion aux standards automatiques ou aux files d’attente d’appels est autorisée.

Si l’utilisateur dispose d’une licence d’audioconférence, il doit démarrer une conférence avec les utilisateurs concernés et appeler le RTC via le pont de conférence pour démarrer une téléconférence. Si l’utilisateur est déjà sur un appel RTC, il peut ajouter un autre utilisateur ou numéro RTC à l’appel via l’escalade de l’appel à l’aide du pont de conférence pour composer.

Dans une téléconférence lancée par un utilisateur sans licence d’audioconférence, l’ajout de participants RTC n’est pas autorisé s’il existe ou a eu au moins un utilisateur Location-Based routage activé dans la téléconférence. Si au moins un participant RTC fait partie ou faisait partie d’une telle téléconférence avant qu’un Location-Based participants activés pour le routage n’ait été invité à participer à l’appel, ces Location-Based participants activés pour le routage ne peuvent pas être ajoutés à l’appel.

Si l’utilisateur activé pour le routage Location-Based rejoint la téléconférence à partir d’un site interne qui n’est pas activé pour le routage Location-Based, les restrictions du paragraphe ci-dessus ne sont pas appliquées. 

La conférence sur le réseau pour l’audioconférence ne doit PAS être déployée avec n’importe quel équipement de téléphonie en Inde.

Un utilisateur Location-Based routage activé sur un appel RTC n’est pas autorisé à fusionner cet appel avec un autre appel.

### <a name="media-bypass-requirement-for-location-based-routing"></a>Configuration requise pour le contournement du média pour le routage Location-Based

Si vous déployez Location-Based routage en Inde, il est nécessaire de configurer également la déviation du trafic multimédia. Pour plus d’informations, consultez [Plan for media bypass with Direct Routing](direct-routing-plan-media-bypass.md) and [Local Media Optimization for Direct Routing](direct-routing-media-optimization.md).

### <a name="direct-voice-over-ip-voip"></a>Voix directe sur IP (VoIP)

La voix directe sur IP (VoIP) ne doit pas être déployée avec des équipements de téléphonie en Inde.


## <a name="related-articles"></a>Articles connexes

- [Activer le routage géodépendant pour le routage direct](location-based-routing-enable.md)
- [Paramètres réseau pour les fonctionnalités de voix cloud dans Teams](cloud-voice-network-settings.md)
