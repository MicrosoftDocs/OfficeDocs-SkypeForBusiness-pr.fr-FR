---
title: Configurer l’optimisation des médias locaux pour le routage direct
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 04/07/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: filippse
search.appverid: MET150
f1.keywords:
- NOCSH
description: Configurer l’optimisation des médias locaux pour le routage direct
appliesto:
- Microsoft Teams
ms.openlocfilehash: 58cf5f560a22a58cb76ea28389d0dce1e3b3f4fb
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674876"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a>Configurer l’optimisation des médias locaux pour le routage direct

La configuration pour l’optimisation des médias locaux est basée sur des paramètres réseau communs à d’autres fonctionnalités de voix cloud, telles que le routage Location-Based et les appels d’urgence dynamiques. Pour en savoir plus sur les régions réseau, les sites réseau, les sous-réseaux réseau et les adresses IP approuvées, consultez [Paramètres réseau pour les fonctionnalités de voix cloud](cloud-voice-network-settings.md).

Avant de configurer l’optimisation des médias locaux, consultez [Optimisation des médias locaux pour le routage direct](direct-routing-media-optimization.md).

Pour configurer l’optimisation des médias locaux, les étapes suivantes sont requises. Vous pouvez utiliser le centre Teams Administration ou PowerShell. Pour plus d’informations, consultez [Gérer la topologie de votre réseau](manage-your-network-topology.md).

1. Configurez l’utilisateur et les sites SBC (comme décrit dans cet article).
2. Configurez les SBC pour l’optimisation des médias locaux (selon la spécification de votre fournisseur SBC).

Le diagramme suivant montre la configuration réseau utilisée dans les exemples de cet article.

> [!div class="mx-imgBorder"]
> ![Diagramme montrant la configuration réseau pour des exemples.](media/direct-routing-media-op-9.png "Configuration réseau pour des exemples")

## <a name="configure-the-user-and-the-sbc-sites"></a>Configurer l’utilisateur et les sites SBC

Pour configurer l’utilisateur et les sites SBC, vous devez :

1. [Gérer les adresses IP approuvées externes](#manage-external-trusted-ip-addresses).

2. [Définissez la topologie réseau](#define-the-network-topology) en configurant les régions réseau, les sites réseau et les sous-réseaux réseau.

3. [Définissez la topologie de réseau virtuel](#define-the-virtual-network-topology) en affectant des SBC à des sites avec des modes pertinents et des valeurs SBC proxy.

> [!NOTE]
> L’optimisation des médias locaux s’appuie sur les emplacements clients détectés en tant qu’emplacements externes ou internes par rapport aux réseaux d’entreprise avec accès à une interface interne du contrôleur de frontière de session (SBC) de routage direct (DR).
> Dans les scénarios VPN de tunnel fractionné lorsque le point de terminaison client est détecté comme externe au réseau du client, Microsoft signale l’emplacement externe au SBC, même si le client peut atteindre l’interface interne du SBC de routage direct du client. Les clients de routage direct utilisant l’optimisation des médias locaux peuvent subir des temps d’installation d’appel prolongés et, dans certains cas, aucun audio lors de la réception d’appels à partir du RTC.
> Pour éviter cela, les administrateurs VPN doivent bloquer l’accès entre les utilisateurs VPN distants et l’interface interne SBC de routage direct.

## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a>Configurer des SBC pour l’optimisation des médias locaux en fonction de la spécification du fournisseur SBC

Cet article décrit la configuration des composants Microsoft. Pour plus d’informations sur la configuration de SBC, consultez la documentation de votre fournisseur SBC. Pour plus d’informations sur les fournisseurs SBC qui prennent en charge l’optimisation des médias locaux, consultez [Contrôleurs de bordure de session certifiés pour le routage direct](direct-routing-border-controllers.md).

## <a name="manage-external-trusted-ip-addresses"></a>Gérer les adresses IP approuvées externes

Les adresses IP approuvées externes sont les adresses IP externes Internet du réseau d’entreprise. Ces adresses IP sont les adresses IP utilisées par Microsoft Teams clients lorsqu’ils se connectent à Microsoft 365. Vous devez ajouter ces adresses IP externes pour chaque site où vous avez des utilisateurs utilisant l’optimisation des médias locaux.

Pour ajouter les adresses IP publiques pour chaque site, utilisez l’applet de commande New-CsTenantTrustedIPAddress. Vous pouvez définir un nombre illimité d’adresses IP approuvées pour un locataire. Si les adresses IP externes vues par Microsoft 365 sont à la fois des adresses IPv4 et IPv6, vous devez ajouter les deux types d’adresses IP. Pour IPv4, utilisez le masque 32. Pour IPv6, utilisez le masque 128. Vous pouvez ajouter des adresses IP externes individuelles et des sous-réseaux IP externes en spécifiant différents MaskBits sur l’applet de commande.

```powershell
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```

Exemple d’ajout d’adresses IP approuvées.

```powershell
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```

## <a name="define-the-network-topology"></a>Définir la topologie de réseau

Cette section explique comment définir les régions réseau, les sites réseau et les sous-réseaux réseau pour votre topologie réseau.

Tous les paramètres respectent la casse. Vous devez donc vous assurer d’utiliser le même cas que celui utilisé lors de l’installation.  (Par exemple, les valeurs GatewaySiteID « Vietnam » et « vietnam » seront traitées comme des sites différents.)

### <a name="define-network-regions"></a>Définir des régions réseau

Pour définir des régions réseau, utilisez l’applet de commande New-CsTenantNetworkRegion. Le paramètre RegionID est un nom logique qui représente la zone géographique de la région et n’a aucune dépendance ou restriction. Le paramètre CentralSite `<site ID>` est facultatif.

```powershell
New-CsTenantNetworkRegion -NetworkRegionID <region ID>
```

L’exemple suivant crée une région réseau nommée APAC :

```powershell
New-CsTenantNetworkRegion -NetworkRegionID "APAC"
```

### <a name="define-network-sites"></a>Définir des sites réseau

Pour définir des sites réseau, utilisez l’applet de commande New-CsTenantNetworkSite. Chaque site réseau doit être associé à une région réseau.

```powershell
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

L’exemple suivant crée trois nouveaux sites réseau, le Vietnam, l’Indonésie et Singapour dans la région APAC :

```powershell
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a>Définir des sous-réseaux réseau

Pour définir des sous-réseaux réseau et les associer à des sites réseau, utilisez l’applet de commande New-CsTenantNetworkSubnet. Chaque sous-réseau réseau ne peut être associé qu’à un seul site.

```powershell
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

L’exemple suivant définit trois sous-réseaux réseau et les associe aux trois sites réseau suivants : Vietnam, Indonésie et Singapour :

```powershell
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID "Vietnam"
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID "Indonesia"
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID "Singapore"
```

## <a name="define-the-virtual-network-topology"></a>Définir la topologie de réseau virtuel

Tout d’abord, l’administrateur client crée une nouvelle configuration SBC pour chaque SBC approprié à l’aide de l’applet de commande New-CsOnlinePSTNGateway.
L’administrateur client définit la topologie de réseau virtuel en spécifiant les sites réseau pour les objets de passerelle RTC à l’aide de l’applet de commande Set-CsOnlinePSTNGateway :

```powershell
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

Remarques :

- Si le client a un seul SBC, le paramètre -ProxySBC doit être obligatoire $null ou la valeur de nom de domaine complet SBC (SBC central avec scénario de jonctions centralisées).
- Le paramètre -MediaBypass doit être défini sur $true afin de prendre en charge l’optimisation des médias locaux.
- Si le paramètre -BypassMode n’est pas défini sur le SBC, les en-têtes X-MS ne sont pas envoyés.
- Tous les paramètres respectent la casse. Vous devez donc vous assurer d’utiliser le même cas que celui utilisé lors de l’installation.  (Par exemple, les valeurs GatewaySiteID « Vietnam » et « vietnam » seront traitées comme des sites différents.)

L’exemple suivant ajoute trois SBC aux sites réseau Vietnam, Indonésie et Singapour dans la région APAC avec le mode Toujours contourner :

```powershell
Set-CSOnlinePSTNGateway -Identity "proxysbc.contoso.com" -GatewaySiteID "Singapore" -MediaBypass $true -BypassMode "Always" -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity "VNsbc.contoso.com" -GatewaySiteID "Vietnam" -MediaBypass $true -BypassMode "Always" -ProxySBC "proxysbc.contoso.com"

Set-CSOnlinePSTNGateway -Identity "IDsbc.contoso.com" -GatewaySiteID "Indonesia" -MediaBypass $true -BypassMode "Always" -ProxySBC "proxysbc.contoso.com"
```

> [!NOTE]
> Pour garantir des opérations ininterrompues lorsque l’optimisation des médias locaux et le routage Location-Based (LBR) sont configurés en même temps, les SBC en aval doivent être activés pour LBR en définissant le paramètre GatewaySiteLbrEnabled sur $true pour chaque SBC en aval. (Ce paramètre n’est pas obligatoire pour le SBC proxy.)

En fonction des informations ci-dessus, le routage direct inclut trois en-têtes SIP propriétaires vers des invitations SIP et des invitations à nouveau, comme indiqué dans le tableau suivant.

En-têtes X-MS introduits dans le routage direct sur invitations et Re-Invites si BypassMode est défini :

|Nom de l’en-tête|Valeurs|Commentaires|
|---|---|---|
|X-MS-UserLocation|interne/externe|Indique si l’utilisateur est interne ou externe|
|Request-URI INVITE sip : +84439263000@VNsbc.contoso.com SIP /2.0|Nom de domaine complet SBC|Nom de domaine complet ciblé pour l’appel, même si le SBC n’est pas directement connecté au routage direct|
|X-MS-MediaPath|Exemple : proxysbc.contoso.com, VNsbc.contoso.com|Ordre des SBC qui doivent être utilisés pour le chemin du média entre l’utilisateur et le SBC cible. Le SBC final est toujours le dernier|
|X-MS-UserSite|usersiteID|Chaîne définie par l’administrateur client|

## <a name="call-flows"></a>Flux d’appels

L’exemple suivant montre les flux d’appels pour deux modes :

- [Toujours contourner](#always-bypass-mode)
- [Uniquement pour les utilisateurs locaux](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a>Toujours contourner le mode

Le mode Always Bypass est l’option la plus simple à configurer. L’administrateur client peut configurer un site unique pour tous les utilisateurs et les SBC si tous les SBC sont accessibles à partir de n’importe quel site.

Les exemples montrent le mode de contournement Always pour les scénarios suivants :

- [Appels sortants et l’utilisateur se trouve au même emplacement que le SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [Appels entrants et l’utilisateur se trouve au même emplacement que le SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [Appels sortants et l’utilisateur externe](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [Appels entrants et l’utilisateur externe](#inbound-calls-and-the-user-is-external-with-always-bypass)

Le tableau suivant montre le nom de domaine complet et les adresses IP utilisés dans les exemples :

|FQDN|Adresse IP externe SBC|Adresse IP interne SBC|Sous-réseau interne|Lieu|NAT externe (adresse IP approuvée)|
|---|---|---|---|---|---|
|VNsbc.contoso.com|Aucun|192.168.1.5|192.168.1.0/24|Vietnam|172.16.240.110|
|IDsbc.contoso.com|Aucun|192.168.2.5|192.168.2.0/24|Indonésie|172.16.240.120|
|proxysbc.contoso.com|172.16.240.133|192.168.3.5|192.168.3.0/24|Singapour|172.16.240.130|

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a>Appels sortants et l’utilisateur se trouve au même emplacement que le SBC avec Always Bypass

|Mode|Utilisateur|Lieu|Sens de l’appel|
|---|---|---|---|
|AlwaysBypass|Interne|Le même site que SBC|Sortant|

Le tableau suivant présente la configuration et l’action de l’utilisateur final :

|Emplacement physique de l’utilisateur|L’utilisateur effectue ou reçoit un appel vers/à partir d’un numéro|Numéro de téléphone de l’utilisateur|Stratégie de routage vocal en ligne|Mode configuré pour SBC|
|---|---|---|---|---|
|Vietnam|+84 4 3926 3000|+84 4 5555 5555|Priorité 1 : ^\+84(\d{9})$ -VNsbc.contoso.com <br> Priorité 2 : .* - proxysbc.contoso.com|VNsbc.contoso.com – Toujours contourner <br> proxysbc.contoso.com : Toujours contourner|

Le diagramme suivant montre l’échelle SIP pour un appel sortant avec le mode de contournement Always et l’utilisateur au même emplacement que le SBC.

> [!div class="mx-imgBorder"]
> ![Diagramme montrant les appels sortants.](media/direct-routing-media-op-10.png "Appels sortants")

Le tableau suivant présente les en-têtes X-MS envoyés par le routage direct :

|Paramètre|Explication|
|---|---|
|Inviter +8443926300@VNsbc.contoso.com|Le nom de domaine complet cible du SBC tel que défini dans la stratégie de routage vocal en ligne est envoyé dans l’URI de requête.|
|X-MS-UserLocation : interne|Le champ indique que l’utilisateur se trouve à l’intérieur du réseau d’entreprise|
|X-MS-MediaPath : VNsbc.contoso.com|Spécifie le SBC que le client doit parcourir jusqu’au SBC cible. Dans ce cas, comme nous avons Always Bypass, et le client est interne le nom cible envoyé comme seul nom dans l’en-tête.|
|X-MS-UserSite: Vietnam|Champ indiqué dans le site où se trouve l’utilisateur.|

#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a>Appels entrants et l’utilisateur se trouve au même emplacement que le SBC avec Always Bypass

|Mode|Utilisateur|Lieu|Sens de l’appel|
|---|---|---|---|---|
|AlwaysBypass|Interne|Le même site que SBC|Entrants|

Lors d’un appel entrant, l’emplacement de l’utilisateur est inconnu et le SBC doit deviner où se trouve l’utilisateur. Si l’estimation n’est pas correcte, une nouvelle invitation est nécessaire. Ce cas suppose que l’utilisateur est interne, que le média peut circuler directement et qu’aucune autre action n’est requise (ré-invitation).
Le SBC connecté au service de routage direct signale l’emplacement SBC d’origine en fournissant des champs Record-Route et Contact. En fonction de ces champs, le chemin d’accès multimédia est calculé par routage direct.

Remarque : Étant donné qu’un utilisateur peut avoir plusieurs points de terminaison, la prise en charge de 183 n’est pas possible. Dans ce cas, le routage direct utilise toujours 180 sonneries.

Le diagramme suivant montre l’échelle SIP pour les appels entrants avec le mode AlwaysBypass, et l’utilisateur se trouve au même emplacement que le SBC.

> [!div class="mx-imgBorder"]
> ![Diagramme montrant l’échelle SIP.](media/direct-routing-media-op-11.png)

#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a>Appels sortants et l’utilisateur externe avec Always Bypass

|Mode|Utilisateur|Site|Sens de l’appel
|---|---|---|---|
|AlwaysBypass|Externe|N/A|Sortant|

Le diagramme suivant montre l’échelle SIP pour un appel sortant avec le mode AlwaysBypass, et l’utilisateur est externe :

> [!div class="mx-imgBorder"]
> ![Diagramme montrant l’échelle SIP.](media/direct-routing-media-op-12.png)

Le tableau suivant présente les en-têtes X-MS envoyés par le service de routage direct :

|Paramètre|Explication|
|---|---|
|Inviter +8443926300@VNsbc.contoso.com|Le nom de domaine complet cible du SBC tel que défini dans la stratégie de routage vocal en ligne est envoyé dans l’URI de requête.|
|X-MS-UserLocation : externe|Le champ indique que l’utilisateur se trouve en dehors du réseau d’entreprise.|
|X-MS-MediaPath : proxysbc.contoso.com, VNsbc.contoso.com|Spécifie le SBC que le client doit parcourir jusqu’au SBC cible. Dans ce cas, comme nous avons Always Bypass, et le client est externe.|

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a>Appels entrants et l’utilisateur externe avec Always Bypass

|Mode|Utilisateur|Site|Sens de l’appel|
|---|---|---|---|
|AlwaysBypass|Externe|N/A|Entrants|

Pour un appel entrant, le SBC connecté au routage direct doit envoyer une nouvelle invitation (par défaut, les candidats aux médias locaux sont toujours proposés) si l’emplacement de l’utilisateur est externe.  X-MediaPath est calculé en fonction de Record-Route et de l’utilisateur SBC spécifié.

Le diagramme suivant montre l’échelle SIP pour un appel entrant avec le mode AlwaysBypass, et l’utilisateur est externe.

> [!div class="mx-imgBorder"]
> ![Diagramme montrant à nouveau l’échelle SIP.](media/direct-routing-media-op-13.png)

### <a name="only-for-local-users-mode"></a>Uniquement pour les utilisateurs locaux en mode

Les candidats multimédias locaux du SBC cible sont proposés uniquement si un utilisateur se trouve au même emplacement que le SBC. Dans tous les autres cas, le média transite par une adresse IP interne ou externe du SBC proxy.

Les scénarios suivants sont décrits :

- [Appels sortants et l’utilisateur se trouve au même emplacement que le SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [Appels entrants et l’utilisateur se trouve au même emplacement que le SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [L’utilisateur n’est pas au même emplacement que le SBC, mais il se trouve dans le réseau d’entreprise](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [Appels entrants et l’utilisateur est interne, mais n’est pas au même emplacement que le SBC](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

Le tableau suivant présente la configuration et l’action de l’utilisateur final :

|Emplacement physique de l’utilisateur|L’utilisateur effectue ou reçoit un appel vers/à partir d’un numéro|Numéro de téléphone de l’utilisateur|Stratégie de routage vocal en ligne|Mode configuré pour SBC|
|---|---|---|---|---|
|Vietnam|+84 4 3926  3000|+84 4 5555 5555|Priorité 1 : ^\+84(\d{9})$ -VNsbc.contoso.com <br> Priorité 2 : .* - proxysbc.contoso.com|VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Toujours contourner|

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a>Appels sortants et l’utilisateur se trouve au même emplacement que le SBC avec uniquement pour les utilisateurs locaux

|Mode|Utilisateur|Site|Sens de l’appel|
|---|---|---|---|
|OnlyForLocalUsers|Interne|Identique à SBC|Sortant|

Le diagramme suivant montre un appel sortant avec le mode OnlyForLocalUsers, et l’utilisateur se trouve au même emplacement que le SBC. Il s’agit du même flux que celui indiqué dans les [appels sortants lorsque l’utilisateur se trouve au même emplacement que le SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).

> [!div class="mx-imgBorder"]
> ![Le diagramme montre à nouveau l’échelle SIP.](media/direct-routing-media-op-14.png)

#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a>Appels entrants et l’utilisateur se trouve au même emplacement que le SBC avec uniquement pour les utilisateurs locaux

|Mode|Utilisateur|Site|Sens de l’appel|
|---|---|---|---|
|OnlyForLocalUsers|Interne|Identique à SBC|Entrants|

Le diagramme suivant montre un appel entrant avec le mode OnlyForLocalUsers, et l’utilisateur se trouve au même emplacement que le SBC. Il s’agit du même flux que celui indiqué dans les [appels entrants lorsque l’utilisateur se trouve au même emplacement que le SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).

> [!div class="mx-imgBorder"]
> ![Autre diagramme montrant l’échelle SIP.](media/direct-routing-media-op-15.png)

#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a>L’utilisateur n’est pas au même emplacement que le SBC, mais il se trouve dans le réseau d’entreprise avec Uniquement pour les utilisateurs locaux

|Mode|Utilisateur|Site|Sens de l’appel|
|---|---|---|---|
|OnlyForLocalUsers|Interne|Différent de SBC|Sortant|

Le routage direct calcule X-MediaPath en fonction de l’emplacement signalé de l’utilisateur et du mode configurés sur le SBC.

Le diagramme suivant montre un appel sortant avec le mode OnlyForLocalUsers et un utilisateur interne qui n’est pas au même emplacement que le SBC.

> [!div class="mx-imgBorder"]
> ![Un autre diagramme montre l’échelle SIP.](media/direct-routing-media-op-16.png)

#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a>Appel entrant et l’utilisateur est interne, mais n’est pas au même emplacement que le SBC avec uniquement pour les utilisateurs locaux

|Mode|Utilisateur|Site|Sens de l’appel|
|---|---|---|---|
|OnlyForLocalUsers|Interne|Différent de SBC|Entrants|

Le diagramme suivant montre un appel entrant avec le mode OnlyForLocalUsers et un utilisateur interne qui n’est pas au même emplacement que le SBC.

> [!div class="mx-imgBorder"]
> ![Encore un autre diagramme montrant l’échelle SIP.](media/direct-routing-media-op-17.png)
