---
title: Optimisation des éléments multimédias locaux du routage direct
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
description: Configurer l’optimisation locale des médias pour le routage direct
appliesto:
- Microsoft Teams
ms.openlocfilehash: c3da3cf243b24d0f614c05e9d09eb68796a68545
ms.sourcegitcommit: 296aeac481f901eb9d52b4f12a8c037afc49fa77
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2020
ms.locfileid: "44256489"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a>Configurer l’optimisation locale des médias pour le routage direct

La configuration de l’optimisation des éléments multimédias locaux est basée sur les paramètres réseau communs aux autres fonctionnalités de voix Cloud, telles que le routage par emplacement et les appels d’urgence dynamiques. Pour en savoir plus sur les zones du réseau, les sites réseau, les sous-réseaux réseau et les adresses IP de confiance, voir [paramètres réseau pour les fonctionnalités vocales dans le Cloud](cloud-voice-network-settings.md).

Avant de configurer l’optimisation de média locale, voir [optimisation des médias locaux pour le routage direct](direct-routing-media-optimization.md).  

Pour configurer l’optimisation de média locale, les étapes suivantes sont nécessaires. Vous pouvez utiliser le centre d’administration teams ou PowerShell. Pour plus d’informations, voir [gérer la topologie de votre réseau](manage-your-network-topology.md).

1. Configurez les sites utilisateur et SBC (comme décrit dans cet article).
2. Configurez l’application SBCs pour l’optimisation de média locale (en fonction de la spécification de votre fournisseur SBC).

Le diagramme suivant montre la configuration du réseau utilisée dans les exemples de cet article.

![Diagramme illustrant la configuration réseau pour les exemples](media/direct-routing-media-op-9.png "Configuration du réseau pour les exemples")


## <a name="configure-the-user-and-the-sbc-sites"></a>Configurer l’utilisateur et les sites SBC

Pour configurer l’utilisateur et les sites SBC, vous devez :

1. [Gérer les adresses IP de confiance externes](#manage-external-trusted-ip-addresses).  

2. [Définissez la topologie du réseau](#define-the-network-topology) en configurant les zones du réseau, les sites réseau et les sous-réseaux réseau.

3. [Définissez la topologie du réseau virtuel](#define-the-virtual-network-topology) en assignant des SBC (s) aux sites avec des modes pertinents et des valeurs SBC de proxy.


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a>Configurer des SBC pour optimiser les médias locaux conformément à la spécification du fournisseur de SBC

Cet article décrit la configuration des composants Microsoft. Pour plus d’informations sur la configuration d’un SBC, consultez la documentation de votre fournisseur SBC.

L’optimisation des éléments multimédias locaux est prise en charge par les fournisseurs de SBC suivants :

| Fournisseur | Product |    Version du logiciel |
|:------------|:-------|:-------| :-------|
| [CodesAudio](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    Mediant 500 SBC |   7.20 a. 256 | 
|            |  Mediant 800 SBC |   7.20 a. 256 | 
|            |  Mediant 2600 SBC |  7.20 a. 256 | 
|            |  Mediant 4000 SBC |  7.20 a. 256 | 
|            |  1000B SBC | 7.20 a. 256 | 
|            |  SBC-9000 |  7.20 a. 256 | 
|            |  SBC-édition virtuelle-SBC |   7.20 a. 256 | 
|            |  SBC édition Cloud-SBC | 7.20 a. 256 |
| [Noyau SBC du ruban](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  SBC 5110         | 8,2  |
|            |  SBC 5210         | 8,2  |
|            |  SBC 5400         | 8,2  |
|            |  SBC 7000         | 8,2  |
|            |  SBC SWe          | 8,2  |
| [TE-SYSTEMS](https://www.anynode.de/local_media_optimization/) |  anynode          | 4.0.1 + |
| [Oracle](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | AP 1100 | 8.4.0.0.0 |
|        | AP 3900 | 8.4.0.0.0 |
|        | AP 4600 | 8.4.0.0.0 | 
|        | AP 6300 | 8.4.0.0.0 |
|        | AP 6350 | 8.4.0.0.0 | 
|        | VME     | 8.4.0.0.0 |


## <a name="manage-external-trusted-ip-addresses"></a>Gérer les adresses IP de confiance externes

Les adresses IP approuvées externes sont les adresses IP externes Internet du réseau d’entreprise. Ces adresses IP sont utilisées par les clients Microsoft teams lorsqu’ils se connectent à Microsoft 365. Vous devez ajouter ces adresses IP externes pour chaque site sur lequel les utilisateurs ont recours à une optimisation de média locale.

Pour ajouter les adresses IP publiques pour chaque site, utilisez l’applet de nouvelle applet de nouveau-CsTenantTrustedIPAddress. Vous pouvez définir un nombre illimité d’adresses IP de confiance pour un client. Si la prévention des intrusions externes observée par Microsoft 365 est une adresse IPv4 et IPv6, vous devez ajouter les deux types d’adresses IP. Pour IPv4, utilisez Mask 32. Pour IPv6, utilisez Mask 128. Vous pouvez ajouter des adresses IP externes individuelles et des sous-réseaux IP externes en spécifiant des MaskBits différentes sur l’applet de la cmdlet.

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


Exemple d’ajout d’adresses IP approuvées.

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a>Définissez la topologie du réseau.

Cette section décrit comment définir les régions réseau, les sites réseau et les sous-réseaux pour votre topologie réseau.

Tous les paramètres respectent la casse, de sorte que vous devez vous assurer que vous utilisez la même casse que celle utilisée lors de l’installation.  (Par exemple, les valeurs GatewaySiteID "Vietnam" et "Viêt Nam" seront considérées comme des sites différents.)

### <a name="define-network-regions"></a>Définir des régions réseau

Pour définir les zones du réseau, utilisez l’applet de nouvelle applet de nouveau-CsTenantNetworkRegion. Le paramètre RegionID est un nom logique qui représente la géographie de la région et qui ne possède pas de dépendances ni de restrictions. Le <site ID> paramètre CentralSite est facultatif.

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

L’exemple suivant permet de créer une zone de réseau nommée APAC :

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a>Définir des sites réseau

Pour définir des sites réseau, utilisez l’applet de nouvelle applet de nouveau-CsTenantNetworkSite. Chaque site réseau doit être associé à une région réseau.

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

L’exemple suivant crée trois nouveaux sites réseau, le Viêt Nam, l’Indonésie et Singapour dans la région APAC :

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a>Définir des sous-réseaux réseau

Pour définir des sous-réseaux réseau et les associer à des sites réseau, utilisez l’applet de nouvelle applet de nouveau-CsTenantNetworkSubnet. Chaque sous-réseau ne peut être associé qu’à un seul site. 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

L’exemple suivant définit trois sous-réseaux réseau et les associe aux trois sites réseau : Vietnam, Indonésie et Singapour :

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a>Définir la topologie du réseau virtuel 

Tout d’abord, l’administrateur client crée une nouvelle configuration SBC pour chaque SBC appropriée à l’aide de l’applet de nouvelle cmdlet New-CsOnlinePSTNGateway.
L’administrateur client définit la topologie du réseau virtuel en spécifiant les sites réseau pour les objets passerelle PSTN à l’aide de l’applet de connexion Set-CsOnlinePSTNGateway :

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

Notez ce qui suit : 
   - Si le client dispose d’un SBC unique, le paramètre-ProxySBC doit être obligatoire $null ou une valeur de nom de domaine complet (SBC) (central SBC avec des troncs centralisés).
   - Le paramètre-MediaBypass doit être défini sur $true afin de prendre en charge l’optimisation de média locale.
   - Si le SBC ne dispose pas du jeu de paramètres-BypassMode, les en-têtes X-MS ne seront pas envoyés. 
   - Tous les paramètres respectent la casse, de sorte que vous devez vous assurer que vous utilisez la même casse que celle utilisée lors de l’installation.  (Par exemple, les valeurs GatewaySiteID "Vietnam" et "Viêt Nam" seront considérées comme des sites différents.)

L’exemple suivant ajoute trois SBCs aux sites réseau Vietnam, Indonésie et Singapour dans la région APAC avec le mode toujours contournement :

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

Remarque : pour garantir des opérations ininterrompues lors de la configuration de l’optimisation des médias locaux et du routage basé sur l’emplacement (LBR) en même temps, l’option SBCs en aval doit être activée pour LBR en définissant le paramètre GatewaySiteLbrEnabled sur $true pour chaque SBC en aval. (Ce paramètre n’est pas obligatoire pour l’SBC proxy.)

D’après les informations ci-dessus, le routage direct inclura trois en-têtes SIP propriétaires aux invitations SIP et aux Réinvitations, comme indiqué dans le tableau suivant.

Les en-têtes X-MS introduites dans le routage direct sur les invitations et les Réinvitations si BypassMode est défini :

| Nom de l’en-tête | Doubl | Commentaires | 
|:------------|:-------|:-------|
| X-MS-UserLocation | interne/externe | Indique si l’utilisateur est interne ou externe. |
| Requête-URL d’URL SIP : + 84439263000@VNsbc.contoso.com SIP/2,0 | NOM DE DOMAINE COMPLET SBC | Nom de domaine complet ciblé pour l’appel, même si l’SBC n’est pas directement connecté au routage direct |
| X-MS-MediaPath | Par exemple : proxysbc.contoso.com, VNsbc.contoso.com | Ordre de SBCs à utiliser pour le chemin d’accès multimédia entre l’utilisateur et le SBC cible. Le SBC final est toujours le dernier. |
| X-MS-UserSite | usersiteID | Chaîne définie par l’administrateur client |

## <a name="call-flows"></a>Flux d’appels 

Le code suivant montre les flux d’appels pour deux modes :

- [Contournement permanent](#always-bypass-mode)
- [Uniquement pour les utilisateurs locaux](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a>Mode de contournement toujours

Le mode de contournement toujours est l’option la plus simple à configurer. L’administrateur client peut configurer un seul site pour tous les utilisateurs et SBCs s’il est joignable sur n’importe quel site.

Les exemples indiquent toujours le mode de contournement pour les scénarios suivants :

- [Les appels sortants et l’utilisateur se trouve au même emplacement que l’SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [Appels entrants et l’utilisateur se trouve au même emplacement que l’SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [Appels sortants et l’utilisateur est externe](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [Appels entrants et l’utilisateur est externe](#inbound-calls-and-the-user-is-external-with-always-bypass)

Le tableau suivant répertorie les adresses de domaine complets et les adresses IP utilisées dans les exemples :

| FQDN | Adresse IP externe d’une SBC | Adresse IP interne de SBC | Sous-réseau interne | Lieu | NAT externe (IP de confiance) |
|:------------|:-------|:-------|:-------|:-------|:-------|
| VNsbc.contoso.com | Aucun | 192.168.1.5 | 192.168.1.0/24 | Vietnam | 172.16.240.110 |
| IDsbc.contoso.com | Aucun | 192.168.2.5 | 192.168.2.0/24 | Indonésie | 172.16.240.120 |
| proxysbc.contoso.com | 172.16.240.133 | 192.168.3.5 | 192.168.3.0/24 | Singapour | 172.16.240.130 |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a>Les appels sortants et l’utilisateur se trouve au même emplacement que l’SBC avec toujours contournement

| Veille |    Utilisateur |  Lieu |  Direction de l’appel |
|:------------|:-------|:-------| :-------|
| AlwaysBypass |    Interne |  Même site qu’SBC |  Sortant |

Le tableau suivant montre la configuration et l’action de l’utilisateur final :

| Emplacement physique de l’utilisateur| Un utilisateur effectue ou reçoit un appel vers ou à partir du numéro | Numéro de téléphone de l’utilisateur  | Politique de routage de la voix en ligne | Mode configuré pour SBC |
|:------------|:-------|:-------|:-------|:-------|
| Vietnam | commande + 84 4 3926 3000 | commande + 84 4 5555 5555   | Priorité 1 : ^ \+ 84 (\d {9} ) $-VNsbc.contoso.com <br> Priorité 2 :. *-proxysbc.contoso.com   | VNsbc.contoso.com : toujours contournement <br> proxysbc.contoso.com : toujours contournement


Le diagramme suivant illustre l’échelle SIP pour un appel sortant avec le mode toujours Bypass et l’utilisateur au même emplacement que l’SBC.

![Diagramme montrant les appels sortants](media/direct-routing-media-op-10.png "Appels sortants")

Le tableau suivant montre les en-têtes X-MS envoyés par le routage direct :

| Paramètre | Explication |
|:------------|:-------|
| Inviter + 8443926300@VNsbc.contoso.com | Le FQDN cible de l’SBC tel qu’il est défini dans la stratégie de routage de la voix en ligne est envoyé dans l’URI de requête | 
| X-MS-UserLocation : Internal | Le champ indique que cet utilisateur se trouve à l’intérieur du réseau d’entreprise |
| X-MS-MediaPath : VNsbc.contoso.com |   Spécifie la SBC que le client doit traverser vers l’SBC cible. Dans le cas présent, il n’existe pas de contournement, et le client est en interne le nom de cible envoyé en tant que nom unique dans l’en-tête. | 
|X-MS-UserSite : Vietnam |   Le champ indiqué dans le site de l’utilisateur. |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a>Appels entrants et l’utilisateur se trouve dans le même emplacement que l’SBC avec toujours contournement

| Veille |    Utilisateur |  Lieu |  Direction de l’appel |
|:------------|:-------|:-------|:-------|:-------|
| AlwaysBypass |    Interne | Même site qu’SBC | Entrant |


Lors d’un appel entrant, l’emplacement de l’utilisateur est inconnu et l’SBC doit deviner l’emplacement de l’utilisateur. Si l’estimation n’est pas correcte, une nouvelle invitation sera requise. Dans le cas présent, l’utilisateur est interne, le média peut être acheminé directement et aucune action supplémentaire n’est nécessaire (réinvitation).
Le SBC connecté au service de routage direct rapporte l’emplacement de l’SBC d’origine en fournissant des champs d’itinéraire d’enregistrement et de contact. En fonction de ces champs, le chemin multimédia est calculé par le routage direct.

Remarque : étant donné qu’un utilisateur peut avoir plusieurs points de terminaison, la prise en charge d' 183 n’est pas possible. Dans le cas présent, le routage direct utilise toujours la sonnerie 180. 

Le diagramme suivant illustre l’échelle SIP pour un appel entrant avec le mode AlwaysBypass et l’utilisateur se trouve au même emplacement que l’SBC.

![Diagramme montrant l’échelle SIP](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a>Les appels sortants et l’utilisateur est externe avec toujours contournement

| Veille |    Utilisateur |  Site |  Direction de l’appel
|:------------|:-------|:-------|:-------|
AlwaysBypass |  Externe |  S/O | Sortant |


Le diagramme suivant illustre l’échelle SIP pour un appel sortant avec le mode AlwaysBypass et l’utilisateur est externe :

![Diagramme montrant l’échelle SIP](media/direct-routing-media-op-12.png)

Le tableau suivant montre les en-têtes X-MS envoyés par le service de routage directe :

| Paramètre |   Explication |
|:------------|:-------|
|Inviter + 8443926300@VNsbc.contoso.com | Le FQDN cible de l’SBC tel qu’il est défini dans la stratégie de routage de la voix en ligne est envoyé dans l’URI de requête.|
| X-MS-UserLocation : externes | Le champ indique que cet utilisateur se trouve en dehors du réseau d’entreprise. |
| X-MS-MediaPath : proxysbc.contoso.com, VNsbc.contoso.com    | Spécifie la SBC que le client doit traverser vers l’SBC cible. Dans le cas présent, il n’existe pas de contournement, et le client est externe. |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a>Les appels entrants et l’utilisateur est externe avec toujours contournement

| Veille | Utilisateur | Site |  Direction de l’appel |
|:------------|:-------|:-------|:-------|
AlwaysBypass |  Externe |  S/O |   Entrant |

Dans le cas d’un appel entrant, l’appel SBC connecté au routage direct doit envoyer une nouvelle invitation (par défaut, les candidats de média local sont toujours proposés) si l’emplacement de l’utilisateur est externe.  Le X-MediaPath est calculé en fonction de record-route et de l’utilisateur SBC spécifié.

Le diagramme suivant illustre l’échelle SIP pour un appel entrant avec le mode AlwaysBypass et l’utilisateur est externe.

![Diagramme montrant l’échelle SIP](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a>Uniquement pour le mode utilisateurs locaux

Les médias de médias locaux des SBC cibles seront proposés uniquement si un utilisateur se trouve au même emplacement que l’SBC. Dans tous les autres cas, le contenu multimédia passe par l’intermédiaire d’une adresse IP interne ou externe du proxy SBC.

Les scénarios suivants sont décrits :

- [Les appels sortants et l’utilisateur se trouve au même emplacement que l’SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [Appels entrants et l’utilisateur se trouve au même emplacement que l’SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [L’utilisateur ne se trouve pas au même emplacement que l’SBC mais il se trouve dans le réseau d’entreprise.](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [Les appels entrants et l’utilisateur est interne, mais pas au même emplacement que l’SBC](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

Le tableau suivant montre la configuration et l’action de l’utilisateur final :

| Emplacement physique de l’utilisateur |  Un utilisateur effectue ou reçoit un appel vers ou à partir du numéro |  Numéro de téléphone de l’utilisateur | Politique de routage de la voix en ligne |   Mode configuré pour SBC |
|:------------|:-------|:-------|:-------|:-------|
| Vietnam | commande + 84 4 3926 3000 |  commande + 84 4 5555 5555 | Priorité 1 : ^ \+ 84 (\d {9} ) $-VNsbc.contoso.com <br> Priorité 2 :. *-proxysbc.contoso.com | VNsbc.contoso.com : OnlyForLocalUsers Proxysbc.contoso.com – toujours contournement |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a>Les appels sortants et l’utilisateur se trouve au même emplacement que l’SBC pour les utilisateurs locaux uniquement.

| Veille | Utilisateur | Site | Direction de l’appel |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers |   Interne |Identique à SBC   | Sortant |

Le diagramme suivant montre un appel sortant avec le mode OnlyForLocalUsers et l’utilisateur se trouve au même emplacement que l’SBC. Ce flux est le même que celui affiché dans les [appels sortants lorsque l’utilisateur se trouve au même emplacement que l’SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).

![Diagramme montrant l’échelle SIP](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a>Appels entrants et l’utilisateur se trouve au même emplacement que l’SBC pour les utilisateurs locaux uniquement

| Veille | Utilisateur | Site | Direction de l’appel |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers |   Interne | Identique à SBC | Entrant |

Le diagramme suivant montre un appel entrant avec le mode OnlyForLocalUsers et l’utilisateur se trouve au même emplacement que l’SBC. Ce flux est le même que celui affiché dans les [appels entrants lorsque l’utilisateur se trouve au même emplacement que l’SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).

![Diagramme montrant l’échelle SIP](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a>L’utilisateur ne se trouve pas au même emplacement que le SBC mais il se trouve sur le réseau d’entreprise uniquement pour les utilisateurs locaux.

| Veille | Utilisateur | Site |Direction de l’appel |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers  | Interne |   Différent de SBC | Sortant |

Le routage direct calcule X-MediaPath en fonction de l’emplacement signalé de l’utilisateur et du mode configurés sur l’SBC.


Le diagramme suivant montre un appel sortant avec le mode OnlyForLocalUsers et un utilisateur interne qui n’est pas au même emplacement que l’SBC.

![Diagramme montrant l’échelle SIP](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a>Les appels entrants et l’utilisateur sont internes, mais ne se trouvent pas dans le même emplacement que l’SBC uniquement pour les utilisateurs locaux.

| Veille |    Utilisateur |  Site |  Direction de l’appel |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers | Interne |    Différent de SBC |    Entrant |

Le diagramme suivant montre un appel entrant avec le mode OnlyForLocalUsers et un utilisateur interne qui n’est pas au même emplacement que l’SBC.

![Diagramme montrant l’échelle SIP](media/direct-routing-media-op-17.png)









