---
title: Optimisation des médias locaux pour le routage direct
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
description: Optimisation des médias locaux pour le routage direct
appliesto:
- Microsoft Teams
ms.openlocfilehash: e30b5928fb775453db9a4b149f4f464b30401a80
ms.sourcegitcommit: 70c07a6b1be81681eec32a89872e2218d70c514d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2021
ms.locfileid: "58866396"
---
# <a name="plan-for-local-media-optimization-for-direct-routing"></a>Planifier l’optimisation des médias locaux pour le routage direct

La voix de réseau téléphonique commuté (PSTN) est considérée comme une application critique pour l’entreprise, avec des attentes élevées en matière de qualité vocale. Le routage direct vous permet de contrôler les flux de trafic de médias pour tenir compte d’une multitude de topologies de réseau et de configurations téléphoniques locales pour diverses entreprises dans le monde entier. 

L’optimisation des médias locaux pour le routage direct vous permet de gérer la qualité vocale en :

-   contrôler le flux du trafic de médias entre Teams clients et les contrôleurs de session en bordure du client.
-   Garder les médias locaux au-delà des limites des sous-réseaux d’entreprise.
-   Autoriser les flux multimédias entre les clients Teams et les SBCs, même si les SBCs se placent derrière des pare-feu d’entreprise avec des IP privés et ne sont pas visibles directement par Microsoft.

L’optimisation des médias locaux prend en charge deux scénarios :

- centralisation de toutes les ligne locales via un SBC centralisé connecté à la ligne SIP (Main Session Initiation Protocol) ; fournir des services de téléphonie à toutes les succursales locales de l’entreprise.

-   création d’une topologie de réseau virtuelle des SBCs (où les SBCS des succursales locales sont connectées à un SBC proxy centralisé qui est visible sur son système Téléphone Microsoft et avec lequel communiquer via son adresse IP externe). Dans une topologie de réseau virtuelle, les SBE en aval communiquent via des IPS internes et ne sont pas directement visibles aux Système téléphonique.

Cet article décrit les fonctionnalités, ainsi que les scénarios et solutions pour les clients. Pour plus d’informations sur la configuration, voir [Configurer l’optimisation des médias locaux.](direct-routing-media-optimization-configure.md) 

  > [!NOTE]
  > Si vous souhaitez garder un média local au-delà des limites de votre intranet, il est recommandé d’optimiser les médias locaux. Si vous utilisez déjà la dérivation média et que vous utilisez uniquement les adresses IP publiques de vos SCS, il n’est pas obligatoire de passer à l’optimisation des médias locaux. Vous pouvez continuer à utiliser la dérivation média. Pour plus d’informations, voir [Planifier la dérivation média.](direct-routing-plan-media-bypass.md)

Pour plus d’informations sur les fournisseurs SBC qui supportent l’optimisation des médias locaux, voir Contrôleurs de session [certifiés pour le routage direct.](direct-routing-border-controllers.md)


## <a name="supported-customer-scenarios"></a>Scénarios clients pris en charge

Pour cette discussion, supposons que Contoso gère plusieurs entreprises dans le monde entier comme suit. (Notez que les régions Europe et APAC ne sont utilisées que comme exemples. Une entreprise peut avoir plusieurs régions avec des exigences similaires.)
 
- **En Europe,** Contoso a des bureaux dans 30 pays environ. Chaque bureau possède son propre système de Exchange privé (PBX). 

  Contoso a été proposé une option pour centraliser les ligne dans un emplacement unique (Amsterdam) pour les 30 bureaux européens. Contoso a déployé le SBC à Amsterdam, fourni suffisamment de bande passante pour passer des appels via l’emplacement centralisé, connecté une ligne SIP centrale à l’emplacement centralisé et commencé à servir tous les lieux européens d’Amsterdam. 

- **Dans la région APAC,** Contoso a plusieurs bureaux dans différents pays. 

  Dans de nombreux pays, l’entreprise dispose toujours de ligne de multiplexage de division d’heures (TDM) dans les succursales locales. La centralisation des ligne TDM n’est pas une option dans la région APAC. Il n’est donc pas possible de basculer vers SIP. Supposons qu’il y a plus de cinq succursales Contoso dans la région APAC qui ont des centaines de passerelles. Dans ce scénario, il n’est pas possible de coupler toutes les passerelles à l’interface de routage direct, en raison de l’absence d’adresses IP publiques et/ou de décomposements Internet locaux. De plus, certains pays imposent des exigences réglementaires qui ne peuvent pas être remplies sans avoir une connectivité réseau PSTN locale.

En fonction de leurs exigences professionnelles, Contoso a implémenté deux solutions avec l’optimisation des médias locaux pour le routage direct :

- **En Europe,** toutes les ligne sont centralisées et les flux de médias entre la base de données SBC centrale et les utilisateurs, en fonction de l’emplacement de l’utilisateur. 

  - Si un utilisateur est connecté au sous-réseau local d’un réseau d’entreprise (autrement dit, l’utilisateur est interne), les médias circulent entre l’adresse IP interne du client SBC central et le client Teams de l’utilisateur. 
  
  - Si un utilisateur est hors des limites du réseau d’entreprise (par exemple, si l’utilisateur utilise une connexion Internet sans fil publique), l’utilisateur est considéré comme externe. Dans ce cas, les médias circulent entre l’adresse IP externe du client SBC central et Teams client.

- Dans la région **APAC,** un SBC proxy centralisé est associé au routage direct Microsoft, ce qui permet de diriger les médias entre l’interface de routage direct et les SBC en aval dans les succursales locales. 

  Les SCS en aval dans les succursales locales ne sont pas directement visibles au routage direct dans l’APAC, mais ils sont couplés à l’aide de l’cmdlet Set-CSOnlinePSTNGateway pour créer une topologie de réseau virtuelle dans Téléphone Microsoft System. Les médias restent toujours locaux lorsque c’est possible. Les utilisateurs externes ont des médias qui circulent entre Teams client et l’adresse IP publique du proxy SBC.


## <a name="central-sbc-with-centralized-trunks"></a>SBC central avec des ligne centralisées

Pour créer une solution dans laquelle les services PSTN sont fournis à toutes les succursales locales via un SBC central unique avec une ligne SIP centralisée connectée, l’administrateur client Contoso associe un SBC (centralsbc.contoso.com) au service . La ligne SIP centralisée est connectée au SBC. 

- Lorsqu’un utilisateur se trouve dans le réseau interne de l’entreprise, le SBC fournit l’adresse IP interne du SBC pour les médias. 

- Lorsqu’un utilisateur est en dehors du réseau d’entreprise, le SBC fournit l’adresse IP externe (publique) du SBC.

> [!NOTE]
> Toutes les valeurs dans les exemples, tableaux ou diagrammes sont présentés uniquement à des fins d’illustration.

Tableau 1. Exemples de paramètres réseau pour les SBCS 


| Lieu | SBC FQDN | Sous-réseau interne | NAT externe (adresse IP fiable) | Adresse IP externe SBC | Adresse IP interne SBC |
|:------------|:-------|:-------|:-------|:-------|:-------|
| Amsterdam | centralsbc.contoso.com | 192.168.5.0/24 | 172.16.76.73 | 172.16.76.71 | 192.168.5.5 |
| Allemagne | Non déployé | 192.168.6.0/24 | 172.16.76.74 | Non déployé |  Non déployé |
| France | Non déployé | 192.168.7.0/24 | 172.16.76.75 | Non déployé |  Non déployé |


### <a name="internal-user"></a>Utilisateur interne

Le diagramme suivant illustre le flux de trafic lorsqu’un utilisateur est connecté au réseau d’entreprise de la filiale ou du site de l’utilisateur. 

En local, l’utilisateur est affecté à la filiale locale en Allemagne. L’utilisateur effectue un appel téléphonique de routage direct via Teams.

- Le client de support Teams de l’utilisateur communique directement à Système téléphonique via l’API REST, mais le média généré pendant l’appel est généré vers l’adresse IP interne du SBC central. 

- Le SBC redirige le flux vers Système téléphonique et le réseau PSTN connecté. 

- Le SBC central n’est visible Système téléphonique via l’adresse IP externe uniquement. 

Diagramme 1. Flux de trafic lorsque l’utilisateur se trouve sur le site « home » avec un SBC centralisé et une ligne SIP centralisée connectée

![Diagramme montrant l’optimisation du flux de trafic multimédia locale.](media/direct-routing-media-op-1.png "Flux de trafic lorsque l’utilisateur se trouve sur un site « domicile » avec SBC centralisé avec ligne SIP centralisée connectée")


### <a name="external-user"></a>Utilisateur externe

Le diagramme suivant illustre le flux de trafic quand un utilisateur n’est pas sur site et n’est pas connecté au réseau d’entreprise (autrement dit, l’appareil de l’utilisateur est connecté à Internet via un appareil mobile ou un Wi-Fi public). L’utilisateur effectue un appel téléphonique de routage direct via Teams :

- Le client Teams de l’utilisateur communique directement à Système téléphonique via l’API REST, mais, dans ce cas, le média généré pendant l’appel est généré vers l’adresse IP externe du SBC central. 

- Le SBC redirige le flux vers Système téléphonique et le réseau PSTN connecté. 

- Le SBC central n’est visible Système téléphonique via l’adresse IP externe uniquement. 

Dans ce cas, le comportement est similaire, que l’utilisateur soit local avec la filiale en Allemagne ou avec une autre succursale. L’utilisateur est considéré comme externe, car il est hors des limites du réseau d’entreprise.

Diagramme 2. Flux de trafic lorsque l’utilisateur est externe avec un SBC centralisé et une ligne SIP centralisée connectée

![Le diagramme montre le flux de trafic de l’optimisation des médias locaux.](media/direct-routing-media-op-2.png "Flux de trafic quand l’utilisateur est externe en cas de SBC centralisé avec ligne SIP centralisée connectée")

## <a name="proxy-sbc-with-connected-downstream-sbcs"></a>Proxy SBC avec SBCs en aval connectés

Pour créer une solution dans laquelle les services PSTN sont fournis dans toutes les succursales locales de la région APAC où la centralisation des ligne TDM n’est pas proposée comme option, l’administrateur Contoso associe un SBC (proxysbc.contoso.com), également appelé SBC proxy, au service de routage direct. 

Ensuite, l’administrateur Contoso ajoute des SBC en aval indiquant qu’ils peuvent être atteints via le serveur proxy SBC proxysbc.contoso.com. En revanche, les SBCs en aval n’ont pas d’IP publics, mais peuvent être affectés aux itinéraires voix. Le tableau ci-dessous montre des exemples de configuration et de paramètres réseau.

Lorsqu’un utilisateur se trouve dans la filiale locale où se trouve le SBC en aval, le trafic de médias circule directement entre l’utilisateur et le SBC en aval local. Si un utilisateur est en dehors du bureau (sur un Internet public), les médias circulent de l’utilisateur vers l’adresse IP publique du SBC proxy, qui le proxédent vers le ou les SBC en aval appropriés.

Tableau 2. Exemples d’informations sur le réseau SBC

| Lieu | SBC FQDN | Sous-réseau interne | NAT externe (adresse IP fiable) | Adresse IP externe SBC  | Adresse IP interne SBC |
|:------------|:-------|:-------|:-------|:-------|:-------|
| Vietnam | VNsbc.contoso.com | 192.168.1.0/24 | 172.16.240.110 | Aucun |  192.168.1.5 |
| Indonésie  | IDsbc.contoso.com | 192.168.2.0/24 | 172.16.240.120 | Aucun |  192.168.2.5 |
| Singapour | proxysbc.contoso.com |   192.168.3.0/24 | 172.16.240.130 | 172.16.240.133 | 192.168.3.5 |



### <a name="internal-user"></a>Utilisateur interne 

Le diagramme suivant illustre le flux de trafic de haut niveau pour le scénario lorsqu’un utilisateur se trouve à l’intérieur du bureau dans la région APAC. L’utilisateur, affecté à une filiale locale au Vietnam et sur site, effectue un appel téléphonique de routage direct via Teams. 

- Le client de support Teams de l’utilisateur communique avec Système téléphonique directement via l’API REST, mais les médias générés pendant l’appel sont générés vers l’adresse IP interne de SBC local.

- Le SBC local redirige le flux vers le serveur proxy SBC à Singapour et vers le réseau PSTN connecté.

-  Le SBC proxy est visible pour Système téléphonique via l’adresse IP externe uniquement et route le flux à partir du SBC en aval (dans ce cas, le SBC local au Vietnam) vers le serveur Système téléphonique. 

- Le SBC en aval dans la filiale locale n’est pas visible à Système téléphonique directement, mais il est mappé dans la topologie de réseau virtuelle définie par l’administrateur Contoso lors de la configuration de l’optimisation des médias locaux.

> [!NOTE]
> Le comportement peut être différent pour les utilisateurs locaux et les utilisateurs non locaux selon le mode d’optimisation des médias local configuré. 

Pour plus d’informations sur les modes possibles et le comportement approprié, voir Configurer l’optimisation des médias locaux.

Diagramme 3. Flux de trafic lorsque l’utilisateur se trouve sur le réseau « domicile » avec un SBC proxy et des SBC en aval connectés 

![Diagramme à nouveau montrant l’optimisation du flux de trafic multimédia locale.](media/direct-routing-media-op-3.png "Flux de trafic en cas de SBC proxy avec SBC en aval connectés lorsque l’utilisateur se trouve sur le réseau « domicile »")

### <a name="external-user"></a>Utilisateur externe

Le diagramme suivant illustre le flux de trafic lorsqu’un utilisateur est en dehors des limites du réseau d’entreprise. L’utilisateur n’est pas sur site (il n’est pas dans les limites du réseau d’entreprise). L’utilisateur effectue un appel téléphonique de routage direct Teams un numéro de téléphone au Vietnam. 

- Le client Teams de l’utilisateur communique directement avec Système téléphonique via l’API REST, mais le média généré pendant l’appel est d’abord généré vers l’adresse IP externe du proxy SBC à Singapour. 

- En fonction des stratégies de configuration et de voix (voir Configurer l’optimisation des médias [locaux](direct-routing-media-optimization-configure.md) pour plus de détails), le serveur SBC proxy redirige le flux vers le SBC en aval au Vietnam. 

- Le flux SBC en aval au Vietnam redirige le flux vers le réseau PSTN local connecté. 

- Le SBC proxy est visible pour les Système téléphonique via l’adresse IP externe uniquement.

-  Le SBC en aval dans la filiale locale n’est pas visible à Système téléphonique directement, mais il est mappé dans la topologie de réseau virtuelle définie par l’administrateur Contoso lors de la configuration de l’optimisation des médias locaux. Dans l’exemple, l’utilisateur est considéré comme externe, car il est en dehors des limites du réseau d’entreprise. 

Diagramme 4. Flux de trafic lorsque l’utilisateur est externe avec un SBC proxy et des SBC en aval connectés

![De nouveau, le diagramme affiche l’optimisation du flux de trafic multimédia local.](media/direct-routing-media-op-4.png "Flux de trafic en cas de SBC proxy avec SBC en aval connectés lorsque l’utilisateur est externe")

## <a name="local-media-optimization-modes"></a>Modes d’optimisation des médias locaux

L’optimisation des médias locaux prend en charge deux modes :

- **Mode 1 : Toujours contourner.** Dans ce cas, si l’utilisateur est interne, le trafic de médias est circuler dans l’adresse IP interne de SBC en aval local, quel que soit l’emplacement réel de l’utilisateur interne. par exemple, au sein du même bureau que celui où se trouve le SBC en aval ou dans une autre succursale.  

- **Mode 2 : Uniquement pour les utilisateurs locaux.** Dans ce mode, les médias ne sont directement générés qu’à l’adresse IP interne du SBC en aval local, uniquement lorsqu’ils sont générés par l’utilisateur interne situé dans le même bureau que le SBC en aval. 

Pour faire la distinction entre les modes d’optimisation des médias locaux, l’administrateur client doit définir le paramètre -BypassMode sur « Always » ou « OnlyForLocalUsers » pour chaque SBC à l’aide de l'Set-CSonlinePSTNGateway cmdlet. Pour plus d’informations, voir [Configurer l’optimisation des médias locaux.](direct-routing-media-optimization-configure.md)  

> [!NOTE]
> Lorsque les utilisateurs sont internes, une connectivité multimédia entre l’utilisateur et le SBC sur l’adresse IP interne est **requise.** Il n’existe pas de relais de transport public pour les médias dans ce cas, car le SBC fournit une adresse IP interne pour la connectivité multimédia. 

### <a name="mode-1-always-bypass"></a>Mode 1 : Toujours contourner

Si vous avez une bonne connexion entre les succursales, le mode recommandé est Toujours ignorer.
 
Par exemple, supposons qu’une entreprise dispose d’une ligne SIP centralisée à Amsterdam, qui sert 30 pays et dispose d’une bonne connectivité entre les 30 sites et les utilisateurs locaux. Il existe également une branche en Allemagne où un SBC local est déployé.

Le SBC en Allemagne peut être configuré en mode « Toujours contournement ». Les utilisateurs, quel que soit leur emplacement, se connectent au SBC directement via l’adresse IP interne du SBC (par exemple, de France à Allemagne ; voir le diagramme ci-dessous pour référence).

Les deux scénarios suivants sont décrits :

- Scénario 1. L’utilisateur se trouve au même emplacement que le SBC défini dans la stratégie de routage voix en ligne.

- Scénario 2. L’utilisateur et les passerelles se nomment sur différents sites.

#### <a name="scenario-1-the-user-is-in-the-same-location-as-the-sbc-defined-in-the-online-voice-routing-policy"></a>Scénario 1. L’utilisateur se trouve au même emplacement que le SBC défini dans la stratégie de routage voix en ligne

Le SBC d’Amsterdam est configuré pour être un SBC proxy pour un SBC en aval local en Allemagne. L’utilisateur se trouve en Allemagne au sein du même sous-réseau que le réseau d’entreprise du SBC local. Les deux SBCs (proxy et aval) sont configurés pour le mode De contournement toujours. Les stratégies de routage vocal en ligne spécifient qu’en cas d’appels en Allemagne (avec l’code de zone +49), ils doivent être acheminés vers le SBC local en Allemagne. Tous les autres appels (et en cas d’échec du SBC en Allemagne, les appels en Allemagne) doivent être acheminés vers le serveur proxy SBC d’Amsterdam. Le tableau suivant résume l’exemple de configuration. 

Tableau 3. Exemple de configuration pour le scénario 1

| Emplacement physique de l’utilisateur | Un utilisateur appelle un numéro | Stratégie de routage vocal en ligne | Mode configuré pour SBC | Media Flow | 
|:------------|:-------|:-------|:-------|:-------|
| Allemagne | +49 1 437 2800 | Priorité 1 : ^ \+ 49(\d {8} )$ -DEsbc.contoso.com<br>Priorité 2 : .* - proxysbc.contoso.com| DEsbc.contoso.com – Toujours contourner <br>proxysbc.contoso.com – Toujours contourner | Teams Utilisateurs <–> DEsbc.contoso.com |

Le diagramme ci-dessous illustre le flux de trafic de haut niveau pour l’utilisateur interne en Allemagne passant un appel téléphonique de routage direct Teams vers ce numéro en Allemagne. 

- Le client de l’Teams communique directement avec Système téléphonique via l’API REST. 

- Le média généré pendant l’appel est généré vers l’adresse IP interne du SBC local. 

- Le SBC local redirige le flux vers le serveur proxy SBC d’Amsterdam et vers le réseau PSTN connecté. 

- Le SBC proxy est visible aux Système téléphonique via l’adresse IP externe uniquement et route le flux à partir du SBC en aval (en l’occurrence, le SBC local en Allemagne) vers Système téléphonique. 

- Le SBC en aval dans la filiale locale n’est pas visible à Système téléphonique directement, mais il est mappé dans la topologie de réseau virtuelle définie par l’administrateur Contoso lors de la configuration de l’optimisation des médias locaux.


Diagramme 5.  Flux de trafic avec le mode « Toujours contournement » et l’utilisateur se trouve sur le site « domicile »

![Diagramme montrant l’optimisation du flux de trafic multimédia locale.](media/direct-routing-media-op-5.png "Flux de trafic avec le mode « Toujours contournement » et l’utilisateur se trouve sur le site « domicile »")


#### <a name="scenario-2-the-user-and-gateways-are-in-different-sites"></a>Scénario 2 : l’utilisateur et les passerelles se rencontrent sur différents sites

Le SBC d’Amsterdam est configuré pour être un SBC proxy pour un SBC en aval local en Allemagne. Les deux SBCs (proxy et aval) sont configurés pour le mode De contournement toujours. L’utilisateur interne en France, situé dans le siège social de l’agence, passe un appel de routage direct vers l’Allemagne. Les stratégies de routage vocal en ligne spécifient que les appels vers l’Allemagne (avec l’code de zone +49) doivent être acheminés vers le SBC local en Allemagne. Tous les autres appels (et, en cas d’échec du SBC en Allemagne, tous les appels en Allemagne) doivent être acheminés vers le serveur proxy SBC d’Amsterdam. Le tableau suivant résume l’exemple de configuration. 

Tableau 4. Exemple de configuration pour le scénario 2

| Emplacement physique de l’utilisateur | Un utilisateur appelle un numéro | Stratégie de routage vocal en ligne | Mode configuré pour SBC | Media Flow | 
|:------------|:-------|:-------|:-------|:-------|
| France | +49 1 437 2800 | Priorité 1 : ^ \+ 49(\d {8} )$ -DEsbc.contoso.com <br>Priorité 2 : .* - proxysbc.contoso.com |  DEsbc.contoso.com - Toujours contourner proxysbc.contoso.com - Toujours Contourner | Teams Utilisateurs <– > DEsbc.contoso.com  |

Le diagramme suivant illustre le flux de trafic de haut niveau lorsque l’utilisateur allemand interne situé en France effectue un appel téléphonique de routage direct Teams vers le numéro en Allemagne. 

- Le client de l’Teams communique directement avec Système téléphonique via l’API REST.

- Le média généré pendant l’appel est directement généré vers le SBC au cours de l’adresse IP interne de l’Allemagne. 

- Le SBC en Allemagne redirige le flux vers le serveur proxy SBC d’Amsterdam et vers le réseau PSTN connecté. 

Diagramme 6.  Flux de trafic avec le mode « Toujours contournement » et l’utilisateur n’est pas sur le site « domicile » mais dans le réseau interne

![Un diagramme affiche l’optimisation du flux de trafic multimédia locale.](media/direct-routing-media-op-6.png "Flux de trafic avec le mode « Toujours contourner » et l’utilisateur n’est pas sur le site « domicile » mais dans le réseau interne")

### <a name="mode-2-only-for-local-users"></a>Mode 2 : uniquement pour les utilisateurs locaux

Si les connexions entre les succursales locales sont mauvaises, mais bonnes entre les succursales locales et les bureaux régionaux, le mode recommandé est « Uniquement pour les utilisateurs locaux ».

Par exemple, dans la région APAC, supposons que Contoso dispose de plusieurs bureaux dans différents pays. Pour de nombreux pays, il n’est pas possible de passer au sip, car l’entreprise possède toujours des ligne TDM dans de nombreuses succursales locales. La centralisation des ligne TDM n’est pas une option dans la région APAC. En outre, il existe plus d’une centaine de succursales Contoso dans la région APAC qui ont des centaines de passerelles. 

Pour créer une solution dans laquelle les services PSTN sont fournis dans toutes les succursales locales de la région APAC dans laquelle la centralisation des ligne TDM n’est pas proposée comme option, l’administrateur Contoso associe un SBC régional à Singapour en tant que SBC proxy au service de routage direct. La connexion directe entre les succursales locales n’est pas bonne, mais il existe une bonne connexion entre chaque filiale locale et le SBC régional à Singapour. Pour le SBC régional, l’administrateur choisit le mode « Toujours contourner ». Pour les SBC en aval local, l’administrateur choisit le mode « Uniquement pour les utilisateurs locaux ».

Les deux scénarios suivants sont décrits :

- Scénario 1. L’utilisateur se trouve au même emplacement que le SBC défini dans la stratégie de routage voix en ligne

- Scénario 2. L’utilisateur et les passerelles se nomment sur différents sites

#### <a name="scenario-1-the-user-is-in-the-same-location-as-the-sbc-defined-in-online-voice-routing-policy"></a>Scénario 1. L’utilisateur se trouve au même emplacement que le SBC défini dans la stratégie de routage vocale en ligne

Supposons que le SBC de Singapour est configuré pour être un serveur SBC proxy pour les serveurs SBC en aval locaux au Vietnam et en Indonésie. L’utilisateur se trouve au Vietnam au même emplacement que le SBC local. Les stratégies de routage vocal en ligne spécifient que les appels au Vietnam (avec l’code de zone +84) doivent être acheminés vers le SBC local du Vietnam. Tous les autres appels (et, en cas d’échec du SBC au Vietnam, appels au Vietnam), doivent être acheminés vers le serveur proxy SBC à Singapour. Le tableau suivant résume l’exemple de configuration. 

Tableau 5. Exemple de configuration du mode « Uniquement pour les utilisateurs locaux » scénario 1

| Emplacement physique de l’utilisateur | Un utilisateur appelle un numéro | Stratégie de routage vocal en ligne | Mode configuré pour SBC | Media Flow | 
|:------------|:-------|:-------|:-------|:-------|
| Vietnam | +84 4 3926 3000 | Priorité 1 : ^ \+ 84(\d {9} )$ -VNsbc.contoso.com <br>Priorité 2 : .* - proxysbc.contoso.com | VNsbc.contoso.com – Uniquement pour les utilisateurs locaux <br> proxysbc.contoso.com – Toujours contourner | Teams Utilisateurs <-> VNsbc.contoso.com |

Dans le diagramme suivant, un utilisateur affecté à la filiale locale du Vietnam effectue un appel téléphonique de routage direct via Teams. 

- Le client de l’Teams communique directement avec Système téléphonique via l’API REST. 

- Les médias générés pendant les appels sont générés vers l’adresse IP interne du SBC local. 

- Le SBC local redirige le flux vers le serveur proxy SBC à Singapour et vers le réseau PSTN connecté. 

- Le SBC proxy est visible pour Système téléphonique via l’adresse IP externe uniquement et route le flux du SBC en aval (en l’occurrence, le SBC local au Vietnam) vers le serveur Système téléphonique. 

- Le SBC en aval dans la filiale locale n’est pas visible Système téléphonique directement, mais il est mappé dans la topologie de réseau virtuel.

Diagramme 7. Flux de trafic avec le mode « Uniquement pour les utilisateurs locaux » et l’utilisateur se trouve sur le site « domicile »

![Autre diagramme montrant l’optimisation du flux de trafic multimédia locale.](media/direct-routing-media-op-7.png "Flux de trafic avec le mode « Uniquement pour les utilisateurs locaux » et l’utilisateur se trouve sur le site « domicile »")


#### <a name="scenario-2-the-user-and-gateways-are-in-different-sites"></a>Scénario 2. L’utilisateur et les passerelles se nomment sur différents sites

Supposons que le SBC de Singapour est configuré pour être un serveur SBC proxy pour les serveurs SBC en aval locaux au Vietnam et en Indonésie. L’utilisateur interne en Indonésie, situé dans la filiale locale, passe un appel de routage direct vers le Vietnam. Les stratégies de routage voix en ligne spécifient que les appels vers le Vietnam (avec l’code de zone +84) doivent être acheminés vers le SBC local du Vietnam. Tous les autres appels (et, en cas d’échec du SBC au Vietnam, les appels vers le Vietnam) doivent être acheminés vers le serveur proxy SBC à Singapour. Le mode SBC proxy à Singapour est définie sur « Toujours contourner » et le mode SBC local au Vietnam est réglé sur « Uniquement pour les utilisateurs locaux ». Le tableau suivant résume l’exemple de configuration. 

Tableau 6. Configuration utilisateur

| Emplacement physique de l’utilisateur | Un utilisateur appelle un numéro | Stratégie de routage vocal en ligne | Mode configuré pour SBC | Media Flow | 
|:------------|:-------|:-------|:-------|:-------|
| Indonésie | +84 4 3926 3000 | Priorité 1 : ^ \+ 84(\d {9} )$ -VNsbc.contoso.com <br> Priorité 2 : .* - proxysbc.contoso.com |VNsbc.contoso.com – Uniquement pour les utilisateurs locaux <br> proxysbc.contoso.com – Toujours contourner | Teams Utilisateurs <-> proxysbc.contoso.com <-> VNsbc.contoso.com |


Dans le diagramme suivant, l’utilisateur interne effectue un appel téléphonique de routage direct via Teams un numéro en Vietnam. 

- Le client de l’Teams communique directement avec Système téléphonique via l’API REST.

- Les médias générés pendant les appels sont d’abord générés vers l’adresse IP interne du proxy SBC. 

- Le serveur proxy SBC de Singapour redirige le flux vers l’adresse IP interne du SBC en aval au Vietnam et Système téléphonique. 

- Le SBC en aval au Vietnam route le flux vers le réseau PSTN local connecté. 

- Le SBC proxy est visible pour les Système téléphonique via l’adresse IP externe uniquement.

- Les SCS en aval dans les succursales locales ne sont pas visibles Système téléphonique directement, mais sont mappées dans la topologie de réseau virtuelle.

Diagramme 8.  Flux de trafic avec le mode « Uniquement pour les utilisateurs locaux » et l’utilisateur n’est pas sur le site « domicile » mais sur le réseau interne

![Un autre diagramme présente l’optimisation du flux de trafic multimédia locale.](media/direct-routing-media-op-8.png "Flux de trafic avec le mode « Uniquement pour les utilisateurs locaux », l’utilisateur se trouve non pas dans un site « domicile » mais dans un réseau interne")

## <a name="known-issues"></a>Problèmes connus

Voici une liste des problèmes connus actuellement présents dans l’optimisation des médias locaux. Microsoft travaille à la résoudre.

| Problème | Solution de contournement |
| :--- | :--- |
| Teams client n’est pas  identifié comme interne lorsque l’adresse IP publique Teams client correspond à la liste d’adresses IP de confiance du client. | L’optimisation des médias locaux nécessite que Teams sous-réseau du client correspond à un sous-réseau [réseau configuré par le client](/powershell/module/skype/new-cstenantnetworksubnet)|
| Une escalade d’appel entraîne l’abandon d’appels lorsque Teams client est identifié comme interne.| Désactivez l’optimisation des médias locaux sur le SBC de routage direct.|
| Escalade d’appels de 1 à 1 appel entre clients internes en appel à plusieurs avec des clients externes/résultat d’appels supprimés | Travaillez en cours sur un correctif. Vous pouvez également désactiver l’optimisation des médias locaux sur le SBC de routage direct.|
| Teams’utilisateur place l’appel en attente. Musique à l’extrémité du réseau PSTN et l’optimisation des médias locaux fonctionne. L Teams un utilisateur reprend l’appel. L’appel vers le réseau PSTN reprend, mais l’optimisation des médias locaux ne fonctionne pas et l’appel continue via SBC central (proxy) | Lorsqu’un utilisateur appelle un appel pour lancer une musique en attente (MoH), le contrôleur d’appel passe de 1h à 1h à un appel à plusieurs pour appeler le contrôleur de média et le processeur multimédia (également appelé mixer AVMCU) par lequel MoH arrive en attente. L’escalade vers un appel à deux après le reprise ne se produit jamais comme d’après les modèles. Désactivez l’optimisation des médias locaux sur le SBC de routage direct.|
|Pendant quelques secondes, l’utilisateur peut entendre son silence.| En raison de la complexité de l’architecture de l’optimisation des médias locaux, cela peut se produire dans certains cas.|
