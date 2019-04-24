---
title: Flux d'appels avec ExpressRoute
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mpottier, dougand
ms.topic: article
ms.assetid: 413acb29-ad83-4393-9402-51d88e7561ab
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: Cet article décrit les principes du flux d'appels pour Skype Entreprise Online et ExpressRoute, et vous présente des exemples détaillés de flux d'appels afin de vous permettre de comprendre et de planifier correctement.
ms.openlocfilehash: 2406badc671fec8ede36039ebf230115a5920e97
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213022"
---
# <a name="call-flow-using-expressroute"></a>Flux d'appels avec ExpressRoute

Cet article décrit les principes du flux d'appels pour Skype Entreprise Online et ExpressRoute, et vous présente des exemples détaillés de flux d'appels afin de vous permettre de comprendre et de planifier correctement.

Si vous déployez Skype pour Business Online dans le cadre d’Office 365, Skype pour Business Server hybride ou Skype pour l’édition de connecteur Business Cloud, vous devez comprendre afin de la communication entre le Skype pour client d’entreprise et les serveurs et le flux d’appels Vous pouvez efficacement planifier, déployer, utiliser et dépanner votre Skype pour Business Online services.

## <a name="call-flow-overview"></a>Présentation du flux d'appels

Ce document décrit les segments qui peuvent comporter des données pour ces appels flux et vous aide à comprendre le trafic qui restera locales à votre réseau par rapport aux déplacements via Internet ou par le biais de ExpressRoute le trafic réseau. Connaître le trafic qui utilise ExpressRoute vous aideront à évaluer les avantages qui sera envoyé à votre société à l’aide de ExpressRoute, ainsi que vous aident à que comprendre le Guide de déploiement ExpressRoute valider et résoudre les problèmes de votre déploiement une fois que vous avez décidé Pour utiliser ExpressRoute.

Les flux d'appels décrits ici peuvent être influencés par différents facteurs dont vous avez la maîtrise, tels que les règles de pare-feu, la configuration NAT, les proxys et la configuration du routeur. Ce document suppose que les paramètres recommandés ont été appliqués. Ces paramètres recommandés sont décrits dans les sections suivantes :

- [Configurer Skype Entreprise Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

- [URL et plages d'adresses IP Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

- [Vue d’ensemble ExpressRoute](https://docs.microsoft.com/azure/expressroute/expressroute-introduction)

- [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/)

Le programme d’installation et les configurations qui n’ont pas suivi les étapes de configuration de la documentation ci-dessus peuvent avoir des flux des appels différents de ceux que nous avons documentées ici. En outre, vous pouvez trouver vous-même présentant des problèmes de configuration tels que des itinéraires réseau asymétrique et non optimal ou des protocoles non optimal. Routage asymétrique est une considération importante lorsque ExpressRoute est impliqué, car ExpressRoute présente un deuxième chemin d’accès à Office 365, qui crée la possibilité pour un itinéraire qui utilise Internet dans un sens et un autre itinéraire qui utilise le ExpressRoute dans le sens inverse. Cela peut entraîner le trafic bloqué dans le sens de retour si elle traverse le pare-feu.

## <a name="network-segments-and-traffic-types"></a>Segments réseau et types de trafic

### <a name="network-segments"></a>Segments réseau

Avant de pouvoir décrire les flux d'appels, il est important de définir certains termes afin que vous puissiez comprendre les segments réseau et les types de médias utilisés dans Skype Entreprise Online.

Les diagrammes de flux d’appel ci-dessous vous afficher quatre segments réseau différents, chacun d'entre eux sont gérés par les différentes organisations (votre réseau interne, votre fournisseur de services réseau et leurs partenaires Internet et Microsoft) avec différentes caractéristiques de performances. Pour des instructions sur les objectifs de performances réseau, reportez-vous à [la qualité des médias et des performances pour la connectivité réseau dans Skype pour Business Online](media-quality-and-network-connectivity-performance.md).

Vous pouvez voir ci-dessous chacun des segments réseau que nous allons aborder.

![Call Flow Network Segments.](../images/25689bf2-4753-4bea-b8d7-88dc8b6d2e2a.png)

 **Votre réseau** Il s’agit du segment de réseau qui fait partie de votre réseau global que vous pouvez contrôler et gérer. Cela inclut toutes les connexions au sein de votre bureau, si avec ou sans fil, entre bâtiments, aux centres de données locale et vos connexions à des fournisseurs ou partenaires ExpressRoute.

En règle générale, le bord de votre réseau a au moins une zone DMZ avec pare-feu et/ou serveurs proxy, auquel appliquer les stratégies de sécurité de votre organisation et qui n’accepte que certain le trafic réseau que vous avez installé et configuré. Étant donné que vous gérez ce réseau, vous disposez d’un contrôle direct sur les performances de votre réseau et il est fortement recommandé que vous avez terminé évaluations réseau pour valider les performances à la fois dans les sites de votre réseau et de votre réseau à Skype pour les entreprises En ligne. Pour prendre connaissance des exigences en matière de performances, reportez-vous à la rubrique [Qualité des médias et performances de connectivité réseau dans Skype Entreprise Online](media-quality-and-network-connectivity-performance.md).

 **Internet** Il s’agit du segment de réseau qui fait partie de votre réseau global qui sera utilisé par les utilisateurs qui sont connectent à Skype pour Business Online à partir d’en dehors de votre réseau et sont utilisés pour toutes les connexions lorsque ExpressRoute n’est pas configuré. Internet, ainsi que toutes les connexions ne sont pas gérés par vous ou Microsoft, de sorte que les performances et les chemins de routage ne peut pas être déterminés, et il aura le plus grand impact sur le flux des appels et la qualité globale.

 **ExpressRoute** Il s'agit du segment réseau qui fait partie de votre réseau global et vous permet d'établir une connexion dédiée privée au réseau Microsoft. Il s’agit de l’option recommandée pour connecter votre réseau pour le réseau Microsoft (Office 365 de centres de données) pour toutes les charges de travail qui dépendent de la vitesse du réseau et les performances, telles que Skype pour la communication en temps réel Business en ligne. Connexions de ExpressRoute sont établies entre votre réseau et l’utilisation du réseau Microsoft [ExpressRoute les fournisseurs de connectivité](https://azure.microsoft.com/documentation/articles/expressroute-locations/) pour fournir un réseau privé et géré, avec prise en charge de qualité de Service (QoS) qui peut améliorer les performances et de disponibilité de 99,9 % pour les médias en temps réel pendant les périodes de congestion du réseau.

 **Réseau Microsoft** Il s'agit du segment réseau qui fait partie du réseau global qui prend en charge les services Office 365. Ces services comprennent l'ensemble des communications entre les serveurs en ligne pour Office 365. Il peut s’agir du trafic qui traverse le réseau principal Microsoft et transmis entre les régions géographiques.

### <a name="types-of-traffic"></a>Types de trafic

Le trafic réseau Skype pour Business Online se divise en deux grandes catégories, affichés sous forme de chemins d’accès distincts dans le flux des appels :

 **Médias en temps réel** est encapsulées dans RTP (Real-Time Transport Protocol) de données et prend en charge les paramètres audio, vidéo, partage d’application et charges de transfert de fichier. En règle générale, le trafic multimédia étant hautement latence sensible, vous pourriez ce trafic à prendre le chemin le plus direct possible, et pour utiliser le protocole de la couche de transport UDP, car l’aide de TCP présente une latence plus élevée.

 **Signalisation** est la liaison de communication entre le client et serveur, ou les autres clients qui sont utilisés pour contrôler les activités (par exemple, lorsqu’un appel est lancé) et remise de messages instantanés. La majorité du trafic de signalisation utilise le protocole SIP, bien que certains clients utilisent des interfaces REST basées sur HTTP. Pour simplifier, nous envisageons une variété de signalisation qui peuvent transiter via des connexions HTTP et HTTPS ou TLS dans ce type de trafic. Il est important de comprendre que ce trafic est bien moins sensible à la latence, mais qu'il peut entraîner des indisponibilités de service ou des expirations de délai d'appel si la latence entre les points de terminaison excède plusieurs secondes.

Les destinations de ce trafic sont indiquées dans la section [URL et plages d'adresses IP Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) pour tous les services Office 365. Pour chaque URL, il est indiqué si la portion du trafic est susceptible de traverser ExpressRoute pour Office 365. Pour les diagrammes qui montrent que Internet est toujours utilisée pour le trafic lorsque ExpressRoute est activé, consultez [ExpressRoute Azure pour Office 365](https://support.office.com/article/6d2534a2-c19c-4a99-be5e-33a0cee5d3bd). Il est important de comprendre que même des URL qui sont répertoriés comme étant routables sur ExpressRoute sont également routables sur Internet. Cela signifie que dans certains scénarios, la décision si Internet ou ExpressRoute sera utilisé dépend de l’emplacement du client et la configuration des serveurs proxy et les pare-feu. Il est également important de comprendre que depuis pas toutes les URL associé avec Office 365 sont en mesure d’utiliser ExpressRoute, une connexion Internet est requise même si vous achetez ExpressRoute à partir d’un partenaire ExpressRoute.

Le trafic qui ne peut être envoyé via Internet inclut les dépendances Internet courantes, telles que des listes de révocation de certificats (CRL), les recherches DNS et résolution de noms, les URL pour les services partagés Office 365, tels que le centre d’administration Office 365 et certaines non en temps réel fonctions de communication Skype pour Business Online, tels que la télémétrie et fédération pour l’interopérabilité avec Skype consommateur, en tant que bien multimédia qui est un flux pour la diffusion de réunion Skype. Afin de faciliter vos prises de décisions, reportez-vous à la section [Acheminement avec ExpressRoute pour Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408) pour obtenir davantage de détails en vue de la planification du routage de votre réseau.

## <a name="principles-for-call-flows-with-skype-for-business"></a>Principes du flux d'appels avec Skype Entreprise

Avant d'étudier en détails les scénarios de flux d'appels spécifiques, il existe six principes généraux qui vous permettent de comprendre les flux d'appels pour Skype Entreprise.

1. Un Skype pour conférence Business est hébergée dans la même région dans lequel l’organisateur est hébergé. Cela s'applique au cloud Office 365 si l'organisateur est un utilisateur en ligne, ou à un centre de données sur site si l'organisateur de la réunion est un utilisateur sur site.

2. Envoyés à partir d’un client à une conférence hébergée toujours le trafic multimédia accède au serveur où se trouve la conférence. Cela peut être un serveur local au sein d’un centre de données que vous gérez ou un serveur en ligne dans le nuage Office 365. Toutefois, un serveur de périphérie est toujours utilisé pour les flux multimédias de conférences en ligne.

3. Le trafic de médias pour les appels d'égal à égal emprunte la route la plus directe disponible. La route préférée est la route directe jusqu'à l'homologue distant (client). Si toutefois cette route n'est pas disponible en raison du blocage du trafic par le pare-feu ou d'une raison similaire, un ou plusieurs serveurs Edge relaient alors le trafic.

4. Le trafic de signalisation est toujours acheminé vers le serveur sur lequel l'utilisateur est domicilié, c'est-à-dire en ligne ou sur site. Un serveur Edge sera utilisé s'il est impossible d'établir une connexion directe au serveur frontal.

5. Les utilisateurs qui rejoignent une conférence hébergée en ligne utiliseront toujours un serveur Edge (ou deux si les configurations de pare-feu du client le nécessitent).

6. Les utilisateurs qui rejoignent une conférence hébergée sur site n'utiliseront généralement pas de serveur Edge s'ils se connectent depuis le même réseau contenant le déploiement sur site, et ils utiliseront un ou deux serveurs Edge lorsqu'ils se connectent depuis l'extérieur de votre réseau.

Pour obtenir davantage de détails sur la sélection du chemin emprunté par les médias, veuillez vous reporter à la rubrique [ICE - Connectivité Edge des médias](https://aka.ms/AVEdge). Bien que cette vidéo traite de Lync Server 2013, les protocoles et les principes de toujours appliqueront à Skype pour les entreprises.

## <a name="skype-for-business-call-flows-with-expressroute"></a>Flux d'appels Skype Entreprise avec ExpressRoute

Maintenant que vous avez une bonne compréhension de quatre segments réseau différents et certains principes généraux pour Skype pour le flux des appels, vous pouvez utiliser que les informations pour vous aider à comprendre le Skype pour le trafic Business seront parcourir un ExpressRoute segment de réseau.

En règle générale, le trafic réseau traverse la connexion ExpressRoute si l'un des points de terminaison se trouve dans votre réseau et si l'autre point de terminaison se trouve dans le centre de données Office 365. Ce trafic comprend le trafic de signalisation entre le client et le serveur, le trafic de médias utilisé lors des téléconférences, ou les appels d'égal à égal qui utilisent un serveur Edge en ligne.

Le trafic ne traversera pas la connexion ExpressRoute si les deux points de terminaison sont en mesure de communiquer directement sur Internet ou s'ils sont tous les deux situés dans votre réseau. Cela inclut le support pour les appels d’égal à égal, le trafic destiné à un déploiement sur site Internet ou tout le trafic entre les serveurs de périphérie Office 365 Internet. À titre d'exemple, il peut s'agir du trafic d'un utilisateur rejoignant une conférence en ligne depuis un hôtel.

## <a name="basic-skype-for-business-call-flow"></a>Flux d'appel de base Skype Entreprise

Afin de vous aider à mettre en application les principes généraux des flux d'appels Skype Entreprise décrits plus haut, la section suivante de cet article comprend plusieurs diagrammes à des fins de référence. Il ne s'agit pas d'une liste exhaustive des différents flux d'appels existants mais d'une aide en vue de la mise en application des principes détaillés plus haut. En outre, les scénarios décrits dans les diagrammes ont été sélectionnés pour couvrir les types de déploiement courants, notamment en ligne, hybrides, Cloud Connector et dans le cas particulier de la diffusion de réunion Skype.

> [!NOTE]
> Un sous-ensemble de trafic utilisé par Skype pour les entreprises n’est pas routable sur ExpressRoute et prendra toujours un chemin d’accès Internet. Consultez [Office 365 URL et plages d’adresses IP](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) pour déterminer les URL qui peuvent être affectés.

### <a name="peer-to-peer-call-for-office-365-users-from-within-customer-network"></a>Appel d’égal à égal pour les utilisateurs d’Office 365 au sein du réseau de client
<a name="bk_Figure2"> </a>

Pour les appels d'égal à égal, le trafic de médias emprunte toujours la route la plus directe pour parvenir à destination. Toutefois, le trafic de signalisation est acheminé jusqu'au centre de données Office 365 dans lequel l'utilisateur en ligne est domicilié. Étant donné que les deux utilisateurs se trouvent sur le même WAN et que rien n'empêche les clients de communiquer directement, les médias sont acheminés directement entre les deux clients. Le trafic de signalisation, pour les deux utilisateurs, traverse la connexion ExpressRoute destinée au centre de données de chaque organisation. Pour afficher le flux d'appels dans ce scénario, reportez-vous au document suivant.

 **Flux d'appels d'égal à égal**

![Call Flow with Peer to Peer call.](../images/f460369e-bfce-4a03-a031-d7e92c4ace89.png)

### <a name="online-user-on-your-network-joining-a-conference-that-is-hosted-online"></a>Utilisateur en ligne sur votre réseau rejoignant une conférence hébergée en ligne
<a name="bk_Figure3"> </a>

Dans l’exemple d’égal à égal, le trafic multimédia prend toujours l’itinéraire plus direct vers sa destination. Toutefois, pour une conférence en ligne, la destination est dans le nuage Office 365. Cela signifie que le trafic de médias de tous les utilisateurs rejoignant la conférence depuis votre réseau traverse la connexion ExpressRoute et que le trafic de signalisation est acheminé jusqu'au cloud Office 365. Le graphique ci-dessous vous montre que multimédia et la signalisation parcourt la connexion ExpressRoute pour un utilisateur au sein de votre réseau et parcourt directement pour les utilisateurs qui sont connectés à Internet depuis l’extérieur de votre réseau, tels que depuis un café Internet atelier ou hôtel.

N’oubliez pas que l’emplacement d’une conférence est définie par l’organisateur de la réunion et non par les participants. Cela signifie que si la réunion a été planifiée par un client local, le trafic multimédia ne déborder vers le nuage Office 365 ExpressRoute, mais plutôt traversent Internet au centre de données locale de l’organisateur de la réunion.

La destination des médias pour une conférence en ligne sera un centre de données dans le cloud Office 365, le centre de données pouvant toutefois se trouver dans une région géographique différente de celles des utilisateurs qui rejoignent la conférence. Cette situation peut se produire dans deux cas :

- Si l'organisateur de la réunion travaille pour une société différente de celle des participants, et si l'organisation de l'organisateur est hébergée dans une région géographique ou un pays différent

- Si un utilisateur rejoint la réunion depuis une région ou un pays différent de la région ou du pays de l'organisation de la société, soit parce que la société est une multinationale, soit parce que l'utilisateur est en déplacement

La bonne nouvelle sur l’utilisation de ExpressRoute dans ce scénario est qu’avec ExpressRoute complémentaire, les données qui suit le chemin d’accès ExpressRoute passe automatiquement sur une dorsale principale de Microsoft quelle que soit la région géographique de l’organisateur de la réunion Centre de données de l’organisation.

 **Flux d'appels d'un utilisateur en ligne pour une réunion en ligne**

![Call flow for an online hosted conference call.](../images/22d9ee64-b20c-4079-b3d1-a7a806b9a0bc.png)

### <a name="joining-a-conference-hosted-by-on-premises-user-in-hybrid-deployment"></a>Rejoindre une conférence hébergée par un utilisateur sur site dans un déploiement hybride
<a name="bk_Figure3"> </a>

N’oubliez pas que les serveurs de conférence qui prennent en charge des conférences hébergées sont déterminées par hébergeant l’organisateur de la réunion. Dans ce scénario, flux multimédias pour participer à une conférence planifiée par un utilisateur local dans un déploiement hybride de tous les utilisateurs vers un centre de données local. Signalisation pour les utilisateurs hébergés en ligne est établie par le biais de leur organisation dans le nuage Office 365, tandis que media tente une connexion directe. Dans ce scénario, car les deux utilisateurs sont connectent à partir de votre réseau, une connexion directe media étant possible, ExpressRoute est utilisée uniquement pour le trafic pour l’utilisateur hébergé en ligne de signalisation. Si un utilisateur hébergé en ligne se connecte à partir d’Internet, le média peut traverser ExpressRoute si un serveur de périphérie en ligne est utilisé pour se connecter.

 **Flux d'appels d'une conférence hébergée par un utilisateur hybride**

![Call flow hosted onprem.](../images/9e669859-19f3-4a86-95b7-7185eb421ccd.png)

### <a name="on-premises-edge-server-with-office-365-hosted-conferences"></a>Serveur Edge sur site avec conférences hébergées sur Office 365
<a name="bk_Figure5"> </a>

Lorsqu’un utilisateur les jointures hybride en ligne hébergé conférence, nous savons que la signalisation et les médias est destiné au nuage Office 365 et dans la mesure où l’utilisateur provient d’Internet, généralement un chemin d’accès internet direct serait à prendre. Toutefois, dans certains cas, par exemple en raison de restrictions de pare-feu, un chemin d’accès Internet direct n’est pas disponible. Dans ce cas, un serveur de périphérie locaux peut relayer le trafic multimédia, qui entraîne le trafic multimédia revenir à votre réseau local avant d’entamer le circuit ExpressRoute vers le nuage Office 365.

 **Utilisateur sur site rejoignant une téléconférence en ligne à l'aide d'un serveur Edge sur site**

![Call flow for a conference call going through an edge server.](../images/0178c170-5837-430d-84f1-582784bfef55.png)

### <a name="pstn-call-using-skype-for-business-cloud-connector-edition"></a>Appel RTC utilisant Skype Entreprise version Cloud Connector
<a name="bk_Figure6"> </a>

L'utilisation de [Skype Entreprise Online version Cloud Connector](https://aka.ms/CloudConnectorInstaller) offre une connectivité RTC grâce aux ressources sur site telles qu'une jonction SIP ou une passerelle RTC, ou en ayant recours à du matériel léger pour l'intégration avec Skype Entreprise. Avec le nuage connecteur Edition, les utilisateurs sont hébergés en ligne et agissent en tant qu’utilisateurs Online normales lorsqu’ils ne mettent en œuvre des Plans de l’appel. Dans le cadre des appels RTC, le trafic de signalisation est acheminé du client au Cloud au moyen d'une connexion ExpressRoute, si disponible, et le trafic de médias ne sort pas de votre WAN. Dans ce cas, le trafic de signalisation est réacheminé vers le cloud Office 365 jusqu'à atteindre le Cloud Connector.

 **Appel PSTN via le système téléphonique dans Office 365 et nuage connecteur**

![Call flow for a PSTN call using Cloud PBX Cloud Connector.](../images/e48d0f2b-fa1e-4b43-b3dd-d34a33dcdf36.png)

### <a name="skype-meeting-broadcast-with-users-joining-from-customer-network"></a>Diffusion de réunion Skype avec des utilisateurs se connectant depuis le réseau du client
<a name="bk_Figure6"> </a>

La diffusion de réunion Skype est un cas d'utilisation particulier, il s'agit d'une réunion en deux parties, chaque partie présentant un profil de transport réseau différent. La première partie et celle qui est plus importante à partir d’un réseau point de vue des performances, est la réunion interne. Il s’agit de la partie de la réunion qui inclut un ou plusieurs points de terminaison clients se connectant au serveur de conférence dans le nuage Office 365 en temps réel. Données transmises à l’aide de cette partie de la réunion sont exactement comme dans l’exemple ci-dessus, avec une conférence en ligne et de participer à des utilisateurs Office 365.

Diffusion de réunion Skype unique le fait que la réunion est distribuée à un grand nombre de participants à la conférence à l’aide d’une diffusion en continu de service. Cette diffusion en continu de service n’est pas routable sur ExpressRoute, mais utilise à la place Internet avec la prise en charge facultative des services réseau CDN (Content Delivery). Il est utile de reconnaître que la diffusion en continu est un flux multimédias unidirectionnelle étant donné que les participants écoutent mais ne parlez pas et prend en charge la mise en mémoire tampon, il est beaucoup moins sensible aux problèmes de performances réseau telles que la latence, la perte de paquets et la gigue. Au lieu d’optimiser le trafic de diffusion de ces problèmes, il est optimisé pour la bande passante utilisée, car il est potentiellement un très grand nombre de participants recevoir les flux multimédias.

 **Diffusion de réunion Skype avec des utilisateurs depuis le réseau du client**

![Call flow for Skype Meeting Broadcast.](../images/cbe0e9f3-7eee-47e9-b61e-f2780b525dea.png)

## <a name="call-flow-patterns-by-deployment-type"></a>Modèles de flux d'appels par type de déploiement

En commun appeler des exemples de flux ci-dessus et une bonne compréhension des principes généraux qui contrôlent les modèles de trafic, les tableaux ci-dessous fournissent un résumé des modèles de trafic pour une combinaison des scénarios de déploiement et l’utilisation de grande taille. Ces tableaux ne couvrent pas l'intégralité des combinaisons de flux d'appels possibles, mais ils devraient vous aider à comprendre davantage les principes généraux des flux d'appels.

Données sont transmises et sont répertoriées comme étant local de l’organisation ; Il ne laissez le réseau du client, Internet ou ExpressRoute. Les modèles répertoriées ci-dessous sont basées sur les paramètres de réseau les plus courants, tels que des pare-feu, la fédération et Internet et supposent que toutes les entreprises partenaires fédérés ou à plusieurs flux de ExpressRoute. En pratique, avec d'autres paramètres, les modèles de trafic peuvent être différents de ceux répertoriés ci-dessous.

### <a name="call-flows-for-skype-for-business-online"></a>Flux d'appels pour Skype Entreprise Online

Skype pour les scénarios d’utilisation en ligne Business impliquent des utilisateurs qui sont hébergés en ligne et peuvent être appel à partir de votre réseau interne ou Internet. Serveurs locaux ne font pas partie de ces scénarios, afin que toutes les conférences ou du support connexes PSTN passera vers le nuage Office 365 et que les utilisateurs en ligne serveur Edge est également inclus dans le nuage.

 **Flux d'appels résumé pour Skype Entreprise Online**

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Cas d'utilisation** <br/> |**Points de terminaison** <br/> |**Chemin de signalisation** <br/> |**Chemin de médias** <br/> |**Exemple de flux** <br/> |**Remarques** <br/> |
|Appel d'égal à égal  <br/> |Deux clients, tous les deux sur votre réseau.  <br/> |ExpressRoute  <br/> |local  <br/> |[Appel d’égal à égal pour les utilisateurs d’Office 365 au sein du réseau de client](call-flow-using-expressroute.md#bk_Figure2) <br/> ||
|Appel d'égal à égal  <br/> |Deux clients, sur votre réseau (interne) et l’autre client sur Internet (externe).  <br/> |Utilisateur interne : ExpressRoute  <br/> Utilisateur externe : Internet  <br/> |Utilisateur interne : ExpressRoute  <br/> Utilisateur externe : Internet vers serveur Edge Office 365.  <br/> |[Appel d’égal à égal pour les utilisateurs d’Office 365 au sein du réseau de client](call-flow-using-expressroute.md#bk_Figure2) <br/> |Suppose que le pare-feu bloque les connexions entre les clients, ce qui nécessite un serveur de périphérie en ligne directe. Le trafic à partir de l’utilisateur interne au serveur Edge en ligne suit le chemin d’accès que similaire au serveur de conférence de téléconférence.  <br/> |
|Appel d'égal à égal vers un utilisateur dans une organisation fédérée  <br/> |Deux clients, un sur votre réseau (interne) et un utilisateur en ligne sur le réseau de l'organisation fédérée (fédéré).  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Utilisateur en ligne sur votre réseau rejoignant une conférence hébergée en ligne](call-flow-using-expressroute.md#bk_Figure3) <br/> |Suppose qu'un pare-feu bloque les connexions directes entre les clients, serveur Edge en ligne requis. Le trafic provenant de l'utilisateur interne à destination du serveur Edge en ligne suit un chemin similaire à celui d'un serveur de conférence pour une téléconférence.  <br/> |
|Rejoindre une téléconférence organisée par un utilisateur sur le réseau du client  <br/> |Client sur votre réseau et serveur de conférence dans le cloud Office 365.  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Utilisateur en ligne sur votre réseau rejoignant une conférence hébergée en ligne](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Joindre la téléconférence par utilisateur dans Internet  <br/> |Client est sur le serveur Internet et de conférence dans le nuage Office 365.  <br/> |Internet  <br/> |Internet  <br/> |[Utilisateur en ligne sur votre réseau rejoignant une conférence hébergée en ligne](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Rejoindre une conférence hébergée sur un serveur sur site d'une autre société  <br/> |Client sur votre réseau et serveur de conférence dans un centre de données tiers.  <br/> |Internet  <br/> |Internet  <br/> |Non applicable  <br/> |Étant donné que le serveur de conférence qui héberge la conférence se trouve sur le réseau sur site d'un autre client, aucune donnée ne passe par le cloud Microsoft.  <br/> |
|Appel RTC  <br/> |Client dans le réseau du client et les serveurs de système téléphonique dans le nuage Office 365  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Utilisateur en ligne sur votre réseau rejoignant une conférence hébergée en ligne](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Appel RTC  <br/> |Client sur les serveurs Internet et système téléphonique de nuage Office 365  <br/> |Internet  <br/> |Internet  <br/> |Non applicable  <br/> |Le support et la signalisation sera flux dans le centre de données Office 365. Dans la mesure où le point de terminaison client est connecté à Internet, tous les flux de données vers le centre de données Microsoft sur Internet (même si un serveur de périphérie en ligne est nécessaire pour la connectivité).  <br/> |

> [!NOTE]
> ExpressRoute sera utilisé sur le chemin d’accès de média à partir d’un utilisateur situé sur le réseau d’entreprise à un serveur Edge en ligne, mais ne pas être utilisé si le serveur de périphérie pour le déploiement d’un autre client local est utilisé.

### <a name="call-flows-for-skype-for-business-hybrid"></a>Flux d'appels hybride pour Skype Entreprise

Les flux d'appels hybrides sont utilisés lorsque vous disposez d'un déploiement Skype Entreprise comprenant au moins plusieurs utilisateurs domiciliés sur site. Les flux d’appels de cette section incluent les conférences sur site et égal à égal ou PSTN appelle au moins un utilisateur hébergés localement.

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Cas d'utilisation** <br/> |**Points de terminaison** <br/> |**Chemin de signalisation** <br/> |**Chemin de médias** <br/> |**Exemple de flux** <br/> |**Remarques** <br/> |
|Appel d'égal à égal  <br/> |Deux clients, tous les deux sur le réseau du client et domiciliés sur site.  <br/> |Local  <br/> |local  <br/> |[Appel d’égal à égal pour les utilisateurs d’Office 365 au sein du réseau de client](call-flow-using-expressroute.md#bk_Figure2) <br/> |Étant donné que les utilisateurs sont domiciliés sur site, le trafic de signalisation est acheminé vers le centre de données sur site et non vers le cloud Office 365.  <br/> |
|Appel d'égal à égal  <br/> |Deux clients, se connectant tous les deux depuis le réseau du client. L'un d'entre eux est domicilié en ligne, l'autre est domicilié sur site.  <br/> |Utilisateur en ligne : ExpressRoute  <br/> Utilisateur sur site : local  <br/> |local  <br/> |[Appel d’égal à égal pour les utilisateurs d’Office 365 au sein du réseau de client](call-flow-using-expressroute.md#bk_Figure2) <br/> |Seul l'utilisateur domicilié en ligne envoie le trafic de signalisation au cloud Office 365.  <br/> |
|Appel d'égal à égal vers un utilisateur dans une organisation fédérée  <br/> |Deux clients, un utilisateur sur site sur le réseau du client (interne) et un utilisateur en ligne sur le réseau de la société fédérée (fédéré).  <br/> |Utilisateur interne : local  <br/> Utilisateur fédéré : ExpressRoute  <br/> |Internet ou ExpressRoute (selon si un serveur Edge en ligne ou sur site est utilisé)  <br/> |[L’utilisateur en ligne sur votre réseau de participer à une conférence qui est hébergé en ligne](call-flow-using-expressroute.md#bk_Figure3) et une partie du [serveur Edge sur site avec Office 365 hébergé conférences](call-flow-using-expressroute.md#bk_Figure5) (pour le trafic multimédia). <br/> |Suppose qu’un pare-feu bloque les connexions entre les clients, nécessitant le serveur de périphérie en ligne directe. Négociation ICE offre à la fois en ligne (par l’utilisateur en ligne) et les serveurs Edge locaux (par l’utilisateur local) pour la connectivité.  <br/> |
|Rejoindre une conférence organisée par un utilisateur sur le réseau du client (conférence organisée par un utilisateur en ligne).  <br/> |Client sur site sur votre réseau et serveur de conférence dans le cloud Office 365.  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Utilisateur en ligne sur votre réseau rejoignant une conférence hébergée en ligne](call-flow-using-expressroute.md#bk_Figure3) <br/> |Ressources du serveur de conférence téléphonique sont définies par l’organisateur de la réunion. Dans ce cas, la réunion a été organisée par un utilisateur en ligne, les ressources sont par conséquent dans le cloud Office 365.  <br/> |
|Appel RTC  <br/> |Utilisateur sur site sur votre réseau et centre de données Skype Entreprise sur site.  <br/> |Local  <br/> |Local  <br/> |[Appel RTC utilisant Skype Entreprise version Cloud Connector](call-flow-using-expressroute.md#bk_Figure6) <br/> |Scénario similaire à l'utilisation de la version Cloud Connector, sauf que l'utilisateur est domicilié sur site, le trafic de signalisation ne sort donc pas de votre réseau.  <br/> |

### <a name="call-flows-for-skype-for-business-with-cloud-connector"></a>Flux d'appels pour Skype Entreprise avec Cloud Connector

Les utilisateurs qui se connectent à la version Cloud Connector sont tous domiciliés en ligne. Cela signifie que les conférences seront en ligne, et que le trafic de signalisation suivra les mêmes modèles que pour les utilisateurs en ligne. Pour les scénarios autres que les appels RTC, le flux d'appels sera exactement identique au flux décrit ci-dessus pour Skype Entreprise Online.

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Cas d'utilisation** <br/> |**Points de terminaison** <br/> |**Chemin de signalisation** <br/> |**Chemin de médias** <br/> |**Exemple de flux** <br/> |**Remarques** <br/> |
|Appel RTC  <br/> |Utilisateur en ligne sur votre réseau utilisant la version Cloud Connector.  <br/> |local  <br/> |local  <br/> |[Appel RTC utilisant Skype Entreprise version Cloud Connector](call-flow-using-expressroute.md#bk_Figure6) <br/> ||
|Appel RTC  <br/> |Utilisateur en ligne sur Internet utilisant la version Cloud Connector.  <br/> |Internet  <br/> |Internet  <br/> |Combinaison de [serveur Edge sur site avec Office 365 hébergé des conférences](call-flow-using-expressroute.md#bk_Figure5) et [PSTN d’appel à l’aide de Skype pour l’édition de connecteur Business Cloud](call-flow-using-expressroute.md#bk_Figure6).  <br/> |Les utilisateurs sur Internet se connecteront via le serveur Edge inclus dans Cloud Connector, et Cloud Connector se connectera au réseau RTC.  <br/> |

## <a name="related-topics"></a>Voir aussi

[Documentation ExpressRoute](https://go.microsoft.com/fwlink/?LinkId=690285)


