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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Optimization
description: Cet article décrit les principes du flux d'appels pour Skype Entreprise Online et ExpressRoute, et vous présente des exemples détaillés de flux d'appels afin de vous permettre de comprendre et de planifier correctement.
ms.openlocfilehash: b65d7b1e3677c82e562de63257f28ad1561d7190
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164633"
---
# <a name="call-flow-using-expressroute"></a>Flux d'appels avec ExpressRoute

Cet article décrit les principes du flux d'appels pour Skype Entreprise Online et ExpressRoute, et vous présente des exemples détaillés de flux d'appels afin de vous permettre de comprendre et de planifier correctement.

Si vous déployez Skype Entreprise Online dans le cadre de Microsoft 365 ou d’Office 365, de Skype Entreprise Server Hybrid ou de Skype Entreprise version Cloud Connector, vous devez comprendre la communication entre le client et les serveurs Skype Entreprise et le flux d’appels afin de pouvoir planifier, déployer, mettre en service et dépanner vos services Skype Entreprise Online.

## <a name="call-flow-overview"></a>Présentation du flux d'appels

Ce document décrit les segments réseau qui peuvent transporter des données pour ces flux d’appels et vous aide à comprendre le trafic qui restera local par rapport au trafic qui sera acheminé sur Internet ou expressroute. Le fait de savoir quel trafic utilise ExpressRoute vous aide à évaluer les avantages que votre entreprise recevra à l’aide d’ExpressRoute, et vous aide à comprendre les conseils de déploiement d’ExpressRoute pour valider et résoudre les problèmes de votre déploiement une fois que vous avez décidé d’utiliser ExpressRoute.

Les flux d'appels décrits ici peuvent être influencés par différents facteurs dont vous avez la maîtrise, tels que les règles de pare-feu, la configuration NAT, les proxys et la configuration du routeur. Ce document suppose que les paramètres recommandés ont été appliqués. Ces paramètres recommandés sont décrits dans les sections suivantes :

- [Configurer Skype Entreprise Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

- [URL et plages d'adresses IP Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

- [Vue d’ensemble d’ExpressRoute](https://docs.microsoft.com/azure/expressroute/expressroute-introduction)

- [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/)

La configuration et les configurations qui n’ont pas suivi les étapes de configuration de la documentation ci-dessus peuvent avoir des flux d’appels différents de ceux que nous avons consignés ici. En outre, vous pouvez vous poser des problèmes de configuration, tels que des itinéraires réseau asymétriques et non optimaux, ou des protocoles de transport non optimaux. Un routage asymétrique est une préoccupation importante chaque fois qu’ExpressRoute est impliqué, car ExpressRoute introduit un deuxième chemin d’accès à Office 365, ce qui crée la possibilité d’utiliser un itinéraire utilisant Internet dans une direction et un autre itinéraire utilisant ExpressRoute dans le sens inverse. Le trafic peut alors être bloqué dans le sens de retour s’il traverse un pare-feu avec état.

## <a name="network-segments-and-traffic-types"></a>Segments réseau et types de trafic

### <a name="network-segments"></a>Segments réseau

Avant de pouvoir décrire les flux d'appels, il est important de définir certains termes afin que vous puissiez comprendre les segments réseau et les types de médias utilisés dans Skype Entreprise Online.

Les diagrammes de flux d’appels ci-dessous vous montrent quatre segments réseau différents, chacun d’eux sont gérés par des organisations différentes (votre réseau interne, votre fournisseur de services réseau, leurs partenaires de peering Internet et Microsoft) qui ont des caractéristiques de performances différentes. Pour obtenir des instructions concernant les objectifs de performance réseau, reportez-vous à la fonction Qualité des médias et performances de connectivité réseau [dans Skype Entreprise Online.](media-quality-and-network-connectivity-performance.md)

Vous pouvez voir ci-dessous chacun des segments réseau que nous allons aborder.

![Call Flow Network Segments.](../images/25689bf2-4753-4bea-b8d7-88dc8b6d2e2a.png)

 **Votre réseau** Il s’agit du segment réseau qui fait partie du réseau global que vous contrôlez et gérez. Cela inclut toutes vos connexions dans vos bureaux, qu’elles soient câblées ou sans fil, entre vos bureaux, vers des centres de données sur site, et vos connexions à des fournisseurs de services Internet ou à des partenaires ExpressRoute.

En règle générale, la périphérie de votre réseau possède une ou plusieurs DMZ avec des pare-feu et/ou des serveurs proxy, qui appliquent les stratégies de sécurité de votre organisation et qui autorisent uniquement le trafic réseau que vous avez configuré et configuré. Étant donné que vous gérez ce réseau, vous contrôlez directement les performances de votre réseau. Il est vivement recommandé d’effectuer des évaluations du réseau pour valider les performances à la fois sur les sites de votre réseau et à partir de votre réseau vers Skype Entreprise Online. Pour en savoir plus sur les conditions de performances, consultez qualité des médias et performances de [connectivité réseau dans Skype Entreprise Online.](media-quality-and-network-connectivity-performance.md)

 **Internet** Il s’agit du segment réseau qui fait partie du réseau global que les utilisateurs qui se connectent à Skype Entreprise Online depuis l’extérieur de votre réseau et qui sont utilisés pour toutes les connexions quand ExpressRoute n’est pas configuré. Internet et toutes ses connexions ne sont pas gérés par vous ou Microsoft. Les performances et les itinéraires de routage ne peuvent donc pas être déterminés, ce qui a un impact plus important sur le flux d’appels et la qualité globales.

 **ExpressRoute** Il s’agit du segment réseau qui fait partie de votre réseau global, ce qui vous donne une connexion dédiée privée au réseau Microsoft. Il s’agit de l’option recommandée pour connecter votre réseau au réseau Microsoft (centres de données Microsoft 365 ou Office 365) pour toutes les charges de travail dépendant de la vitesse et des performances du réseau, telles que les communications en temps réel Skype Entreprise Online. Les connexions ExpressRoute sont faites entre votre réseau et celui de Microsoft. Elles utilisent des fournisseurs de connectivité [ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-locations/) pour fournir un réseau privé et géré, avec une durée de service de 99,9 % et une prise en charge de la qualité de service (QoS) qui peuvent améliorer les performances des médias en temps réel en cas de congestion du réseau.

 **Réseau Microsoft** Il s’agit du segment réseau qui fait partie du réseau global qui prend en charge les services Microsoft 365 et Office 365. Cela inclut l’ensemble des communications entre les serveurs en ligne pour Microsoft 365 ou Office 365. Cela peut comprendre le trafic qui traverse le réseau de base Microsoft avant d’être transmis entre différentes régions géographiques.

### <a name="types-of-traffic"></a>Types de trafic

Le trafic réseau de Skype Entreprise Online est en deux grandes catégories, représentées par des chemins d’accès distincts dans le flux d’appels :

 **Les médias en temps** réel sont les données encapsulées dans le protocole RTP (Real-time Transport Protocol) et ils prend en charge l’audio, la vidéo, le partage d’application et les charges de travail de transfert de fichiers. En règle générale, le trafic de médias étant très sensible à la latence, vous souhaiteriez que ce trafic utilise le chemin le plus direct possible et utiliser le protocole UDP comme couche transport, car le protocole TCP présente une latence plus élevée.

 **La signalisation** est la liaison de communication entre le client et le serveur, ou d’autres clients utilisés pour contrôler les activités (par exemple, quand un appel est lancé) et envoyer des E-mail. La plupart du trafic de signalisation utilise le protocole SIP, même si certains clients utilisent des interfaces REST basées sur HTTP. Pour faciliter les choses, nous prenons en considération diverses signalisations qui peuvent être circuler sur des connexions HTTP et HTTPS ou TLS dans ce type de trafic. Il est important de comprendre que ce trafic est beaucoup moins sensible à la latence, mais qu’il peut entraîner des induits de service ou des retards d’appel si la latence entre les points de terminaison dépasse plusieurs secondes.

Les destinations de ce trafic sont trouvées dans les URL et [plages d’adresses IP Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) pour tous les services Microsoft 365 ou Office 365. Pour chaque URL, elle indique si cette partie du trafic peut traverser ExpressRoute pour Microsoft 365 ou Office 365. Pour obtenir des diagrammes démonstration que l’Internet est toujours utilisé pour une partie du trafic quand ExpressRoute est activé, consultez Azure ExpressRoute pour [Office 365.](https://support.office.com/article/6d2534a2-c19c-4a99-be5e-33a0cee5d3bd) Il est important de comprendre que même les URL répertoriées comme routables sur ExpressRoute sont également routables sur Internet. Cela signifie que dans certains scénarios, le choix de l’utilisation d’Internet ou d’ExpressRoute dépend de l’emplacement du client et de la configuration des serveurs proxy et des pare-feu. Il est également important de comprendre que, dans la mesure où toutes les URL associées à Microsoft 365 ou Office 365 ne sont pas en mesure d’utiliser ExpressRoute, une connexion Internet est requise même si vous achetez ExpressRoute auprès d’un partenaire ExpressRoute.

Le trafic qui ne peut être envoyé qu’via Internet inclut des dépendances Internet courantes, telles que les listes de révocation de certificats, les listes de choix et la résolution de noms DNS, les URL des services Microsoft 365 ou Office 365 partagés, comme le Centre d’administration Microsoft 365, ainsi que certaines fonctionnalités de communication en temps non réel de Skype Entreprise Online, telles que la télémétrie et la fédération pour l’interopérabilité avec le client Skype, ainsi que des médias diffusés en continu pour la diffusion de réunion Skype. Pour vous aider à prendre des décisions, voir Routage avec ExpressRoute pour [Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408) pour plus d’informations lorsque vous planifiez le routage de votre réseau.

## <a name="principles-for-call-flows-with-skype-for-business"></a>Principes du flux d'appels avec Skype Entreprise

Avant d'étudier en détails les scénarios de flux d'appels spécifiques, il existe six principes généraux qui vous permettent de comprendre les flux d'appels pour Skype Entreprise.

1. Une conférence Skype Entreprise est hébergée dans la région dans laquelle l’organisateur de la conférence est hébergé. Cela s’agit dans le cloud si l’organisateur est un utilisateur en ligne, ou dans un centre de données sur site si l’organisateur de la réunion est un utilisateur sur site.

2. Le trafic de médias envoyé à partir d’un client vers une conférence hébergée passe toujours par le serveur sur lequel la conférence est hébergée. Il peut s’agit d’un serveur local au sein d’un centre de données que vous gérez ou d’un serveur en ligne dans le cloud. Toutefois, un serveur Edge est toujours utilisé pour le flux de médias pour les conférences en ligne.

3. Le trafic de médias pour les appels d'égal à égal emprunte la route la plus directe disponible. La route préférée est la route directe jusqu'à l'homologue distant (client). Si toutefois cette route n'est pas disponible en raison du blocage du trafic par le pare-feu ou d'une raison similaire, un ou plusieurs serveurs Edge relaient alors le trafic.

4. Le trafic de signalisation est toujours acheminé vers le serveur sur lequel l'utilisateur est domicilié, c'est-à-dire en ligne ou sur site. Un serveur Edge sera utilisé s'il est impossible d'établir une connexion directe au serveur frontal.

5. Les utilisateurs qui rejoignent une conférence hébergée en ligne utiliseront toujours un serveur Edge (ou deux si les configurations de pare-feu du client le nécessitent).

6. Les utilisateurs qui rejoignent une conférence hébergée sur site n'utiliseront généralement pas de serveur Edge s'ils se connectent depuis le même réseau contenant le déploiement sur site, et ils utiliseront un ou deux serveurs Edge lorsqu'ils se connectent depuis l'extérieur de votre réseau.

Pour en savoir plus sur le chemin de médias choisi, voir [ICE - Connectivité Edge des](https://aka.ms/AVEdge)médias. Bien que cette vidéo parle de Lync Server 2013, les principes et les protocoles s’appliquent toujours à Skype Entreprise.

## <a name="skype-for-business-call-flows-with-expressroute"></a>Flux d'appels Skype Entreprise avec ExpressRoute

Maintenant que vous avez une compréhension des quatre segments réseau différents et de certains principes directeurs généraux pour les flux d’appels Skype Entreprise, vous pouvez utiliser ces informations pour comprendre quel trafic Skype Entreprise traverse un segment réseau ExpressRoute.

En règle générale, le trafic réseau traverse la connexion ExpressRoute si l’un des points de terminaison se trouve dans votre réseau et si l’autre point de terminaison se trouve dans le centre de données Microsoft 365 ou Office 365. Cela comprend le trafic de signalisation entre le client et le serveur, le trafic de médias utilisé lors des conférences téléphoniques ou les appels d’égal à égal qui utilisent un serveur Edge en ligne.

Le trafic ne traverse pas la connexion ExpressRoute si les deux points de terminaison sont en mesure de communiquer directement sur Internet ou s’ils sont situés au sein de votre réseau. Ce trafic comprend les médias pour les appels d’égal à égal, le trafic provenant d’Internet destiné à un déploiement sur site, ou tout trafic entre Internet et Microsoft 365 ou les serveurs Edge Office 365. À titre d’exemple, un utilisateur rejoint une conférence en ligne depuis un hôtel.

## <a name="basic-skype-for-business-call-flow"></a>Flux d'appel de base Skype Entreprise

Afin de vous aider à mettre en application les principes généraux des flux d'appels Skype Entreprise décrits plus haut, la section suivante de cet article comprend plusieurs diagrammes à des fins de référence. Il ne s'agit pas d'une liste exhaustive des différents flux d'appels existants mais d'une aide en vue de la mise en application des principes détaillés plus haut. En outre, les scénarios décrits dans les diagrammes ont été sélectionnés pour couvrir les types de déploiement courants, notamment en ligne, hybrides, Cloud Connector et dans le cas particulier de la diffusion de réunion Skype.

> [!NOTE]
> Un sous-ensemble du trafic utilisé par Skype Entreprise n’est pas routable sur ExpressRoute et prend toujours un chemin Internet. Reportez-vous [aux URL et plages d’adresses IP Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) pour déterminer les URL qui peuvent être affectées.

### <a name="peer-to-peer-call-for-microsoft-365-or-office-365-user-from-within-customer-network"></a>Appel d’égal à égal pour un utilisateur Microsoft 365 ou Office 365 au sein du réseau du client
<a name="bk_Figure2"> </a>

Pour les appels d’égal à égal, le trafic de médias prend toujours la route la plus directe vers sa destination. Toutefois, le trafic de signalisation est envoyé vers un centre de données Microsoft 365 ou Office 365 dans lequel l’utilisateur en ligne est homed. Étant donné que les deux utilisateurs sont sur le même WAN et que rien n’empêche les clients de communiquer directement, les médias sont directement entre eux. Le trafic de signalisation, pour les deux utilisateurs, traverse la connexion ExpressRoute destinée au centre de données de chaque organisation. Pour afficher le flux d’appels dans ce scénario, consultez ce qui s’affiche.

 **Flux d'appels d'égal à égal**

![Call Flow with Peer to Peer call.](../images/f460369e-bfce-4a03-a031-d7e92c4ace89.png)

### <a name="online-user-on-your-network-joining-a-conference-that-is-hosted-online"></a>Utilisateur en ligne sur votre réseau rejoignant une conférence hébergée en ligne
<a name="bk_Figure3"> </a>

Dans l’exemple d’égal à égal, le trafic de médias prend toujours la route la plus directe vers sa destination. Toutefois, pour une conférence en ligne, la destination se trouve dans le cloud. Cela signifie que le trafic de médias de tous les utilisateurs rejoignant la conférence depuis votre réseau traverse la connexion ExpressRoute et que le trafic de signalisation est acheminé vers le cloud. Le graphique ci-dessous vous montre que le trafic de médias et le trafic de signalisation traverseront la connexion ExpressRoute d’un utilisateur au sein de votre réseau et qu’ils traverseront directement Internet pour les utilisateurs connectés à Internet depuis l’extérieur de votre réseau (par exemple, auprès d’un café ou d’un hôtel).

N’oubliez pas que l’emplacement d’une conférence est défini par l’organisateur de la réunion et non par les participants. Cela signifie que si la réunion est programmée par un client sur site, le trafic de médias ne sera pas acheminé au cloud via ExpressRoute, mais qu’il sera acheminé par Internet jusqu’au centre de données sur site de l’organisateur de la réunion.

La destination des médias pour les conférences en ligne sera un centre de données dans le cloud Microsoft 365 ou Office 365, mais le centre de données peut se trouve dans une région géographique différente de celle des utilisateurs qui rejoignent la conférence. Cela peut se produire de deux façons :

- Si l'organisateur de la réunion travaille pour une société différente de celle des participants, et si l'organisation de l'organisateur est hébergée dans une région géographique ou un pays différent

- Si un utilisateur rejoint la réunion depuis une région ou un pays différent de la région ou du pays de l'organisation de la société, soit parce que la société est une multinationale, soit parce que l'utilisateur est en déplacement

La bonne nouvelle concernant l’utilisation d’ExpressRoute dans ce scénario est qu’avec le module add-on ExpressRoute Premium, les données qui suivent le chemin ExpressRoute passent automatiquement par le réseau principal de Microsoft, quelle que soit la région géographique de l’organisateur de la réunion du centre de données de l’organisation à l’origine de la réunion.

 **Flux d'appels d'un utilisateur en ligne pour une réunion en ligne**

![Call flow for an online hosted conference call.](../images/22d9ee64-b20c-4079-b3d1-a7a806b9a0bc.png)

### <a name="joining-a-conference-hosted-by-on-premises-user-in-hybrid-deployment"></a>Rejoindre une conférence hébergée par un utilisateur sur site dans un déploiement hybride
<a name="bk_Figure3"> </a>

N’oubliez pas que les serveurs de conférence qui supportent des conférences hébergées sont déterminés par la page d’accueil de l’organisateur de la réunion. Dans ce scénario, les médias de tous les utilisateurs rejoignant une conférence organisée par un utilisateur sur site dans un déploiement hybride sont déployés vers un centre de données sur site. Le signalisation des utilisateurs nationaux en ligne sera établi par leur organisation dans le cloud, tandis que le média tentera d’établir une connexion directe. Dans ce scénario, étant donné que les deux utilisateurs se connectent depuis votre réseau, une connexion multimédia directe est possible, ExpressRoute est donc utilisé uniquement pour le trafic de signalisation de l’utilisateur en ligne. Si un utilisateur nationaux en ligne se connecte à partir d’Internet, le trafic de médias peut traverser ExpressRoute si un serveur Edge en ligne est utilisé pour se connecter.

 **Flux d'appels d'une conférence hébergée par un utilisateur hybride**

![Call flow hosted onprem.](../images/9e669859-19f3-4a86-95b7-7185eb421ccd.png)

### <a name="on-premises-edge-server-with-microsoft-365-or-office-365-hosted-conferences"></a>Serveur Edge sur site avec conférences hébergées sur Microsoft 365 ou Office 365
<a name="bk_Figure5"> </a>

Lorsqu’un utilisateur hybride rejoint une conférence hébergée en ligne, nous savons que le trafic de signalisation et le trafic de médias seront destinés au cloud Microsoft 365 ou Office 365, et comme l’utilisateur rejoint la conférence à partir d’Internet, un chemin Internet direct serait normalement tracé. Toutefois, dans certains cas, en raison de restrictions du pare-feu, aucun chemin Internet direct n’est disponible. Dans ce cas, un serveur Edge sur site peut relayer le trafic de médias, ce qui entraîne le retour du trafic de médias sur votre réseau local avant de traverser le circuit ExpressRoute jusqu’au cloud.

 **Utilisateur sur site rejoignant une téléconférence en ligne à l'aide d'un serveur Edge sur site**

![Call flow for a conference call going through an edge server.](../images/0178c170-5837-430d-84f1-582784bfef55.png)

### <a name="pstn-call-using-skype-for-business-cloud-connector-edition"></a>Appel RTC utilisant Skype Entreprise version Cloud Connector
<a name="bk_Figure6"> </a>

L’édition [Cloud Connector](https://aka.ms/CloudConnectorInstaller) de Skype Entreprise Online offre une connectivité PSTN à l’aide de ressources sur site telles qu’une ligne SIP ou une passerelle RSTN, ou en utilisant un matériel minimal pour l’intégration à Skype Entreprise. Avec la version Cloud Connector, les utilisateurs sont homed Online et agissent comme des utilisateurs en ligne normaux lorsqu’ils n’impliquent pas de plans d’appel. Le trafic de signalisation pour les scénarios PSTN est acheminé entre le client et le cloud sur une connexion ExpressRoute, si disponible, et le trafic de médias reste au sein de votre WAN. Dans ce cas, le signalisation est inversement dans le cloud Microsoft 365 ou Office 365 et s’termine au Cloud Connector.

 **Appel PSTN via le système téléphonique dans Microsoft 365 ou Office 365 et Cloud Connector**

![Call flow for a PSTN call using Cloud PBX Cloud Connector.](../images/e48d0f2b-fa1e-4b43-b3dd-d34a33dcdf36.png)

### <a name="skype-meeting-broadcast-with-users-joining-from-customer-network"></a>Diffusion de réunion Skype avec des utilisateurs se connectant depuis le réseau du client
<a name="bk_Figure6"> </a>

La diffusion de réunion Skype est un cas d’utilisation particulier, qui consiste en une réunion en deux parties, chaque partie ayant des profils de transport réseau différents. La première partie, et celle qui est la plus importante d’un point de vue des performances du réseau, est la réunion interne. Il s’agit de la partie en temps réel de la réunion qui comprend un ou plusieurs points de terminaison de client qui se connectent au serveur de conférence dans le cloud. Les données transmises dans cette partie de la réunion sont exactement identiques à l’exemple ci-dessus, avec un utilisateur rejoignant une conférence en ligne.

En quoi la diffusion de réunion Skype est unique, c’est que la réunion est distribuée à un grand nombre de participants à la conférence à l’aide d’un service de diffusion en continu. Ce service de diffusion en continu n’est pas routable sur ExpressRoute, mais utilise Internet avec la prise en charge facultative des services de réseau de distribution de contenu (CDN). Il est utile de reconnaître que la diffusion en continu est un flux multimédia unidirectionnel, car les participants écoutent mais ne parlent pas et ne prend pas en charge la mise en mémoire tampon, il est donc beaucoup moins sensible aux problèmes de performances du réseau tels que la latence, la perte de paquets et la gigue. Au lieu d’optimiser le trafic de diffusion pour ces problèmes, il est optimisé pour l’utilisation de la bande passante, car il est possible qu’un très grand nombre de participants reçoivent le trafic multimédia en continu.

 **Diffusion de réunion Skype avec des utilisateurs depuis le réseau du client**

![Call flow for Skype Meeting Broadcast.](../images/cbe0e9f3-7eee-47e9-b61e-f2780b525dea.png)

## <a name="call-flow-patterns-by-deployment-type"></a>Modèles de flux d'appels par type de déploiement

Avec les exemples courants de flux d’appels ci-dessus et une compréhension des principes généraux qui contrôlent les modèles de trafic, les tableaux ci-dessous fournissent un résumé des modèles de trafic pour de nombreuses combinaisons de scénarios d’utilisation et de déploiement. Ces tableaux ne capturent pas toutes les combinaisons de flux d’appels possibles, mais ils devraient vous aider à mieux comprendre les principes généraux des flux d’appels.

Les données sont transmises et répertoriées comme étant locales pour l’organisation. il ne quitte pas le réseau du client, Internet ou ExpressRoute. Les modèles répertoriés ci-dessous sont basés sur les paramètres réseau les plus courants, tels que les pare-feu, la fédération et Internet, et supposent que toutes les organisations impliquées dans des flux à plusieurs ou fédérés ont ExpressRoute. En pratique, disposer de paramètres différents peut entraîner des modèles de trafic différents de ceux répertoriés ci-dessous.

### <a name="call-flows-for-skype-for-business-online"></a>Flux d'appels pour Skype Entreprise Online

Les scénarios d’utilisation de Skype Entreprise Online impliquent des utilisateurs qui viennent d’être domicile en ligne et peuvent appeler depuis votre réseau interne ou depuis Internet. Ces scénarios ne font pas partie de ces serveurs sur site, tous les médias de conférence ou PSTN sont donc également utilisés dans le cloud, et le serveur Edge des utilisateurs en ligne est également dans le cloud.

 **Flux d'appels résumé pour Skype Entreprise Online**

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Cas d'utilisation** <br/> |**Points de terminaison** <br/> |**Chemin de signalisation** <br/> |**Chemin de médias** <br/> |**Exemple de flux** <br/> |**Remarques** <br/> |
|Appel d'égal à égal  <br/> |Deux clients, tous les deux sur votre réseau.  <br/> |ExpressRoute  <br/> |local  <br/> |[Appel d’égal à égal pour un utilisateur Microsoft 365 ou Office 365 au sein du réseau du client](call-flow-using-expressroute.md#bk_Figure2) <br/> ||
|Appel d'égal à égal  <br/> |Deux clients, un sur votre réseau (interne) et l’autre sur Internet (externe).  <br/> |Utilisateur interne : ExpressRoute  <br/> Utilisateur externe : Internet  <br/> |Utilisateur interne : ExpressRoute  <br/> Utilisateur externe : Internet vers le serveur Microsoft 365 ou Office 365 Edge.  <br/> |[Appel d’égal à égal pour les utilisateurs de Microsoft 365 ou Office 365 au sein du réseau du client](call-flow-using-expressroute.md#bk_Figure2) <br/> |Suppose que le pare-feu bloque les connexions directes entre les clients, serveur Edge en ligne nécessaire. Le trafic provenant d’un utilisateur interne à partir du serveur Edge en ligne suit un chemin similaire à celui d’un serveur de conférence pour une téléconférence.  <br/> |
|Appel d'égal à égal vers un utilisateur dans une organisation fédérée  <br/> |Deux clients, un sur votre réseau (interne) et un utilisateur en ligne sur le réseau de l'organisation fédérée (fédéré).  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Utilisateur en ligne sur votre réseau rejoignant une conférence hébergée en ligne](call-flow-using-expressroute.md#bk_Figure3) <br/> |Suppose qu'un pare-feu bloque les connexions directes entre les clients, serveur Edge en ligne requis. Le trafic provenant de l'utilisateur interne à destination du serveur Edge en ligne suit un chemin similaire à celui d'un serveur de conférence pour une téléconférence.  <br/> |
|Rejoindre une téléconférence organisée par un utilisateur sur le réseau du client  <br/> |Client sur votre réseau et serveur de conférence dans le cloud.  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Utilisateur en ligne sur votre réseau rejoignant une conférence hébergée en ligne](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Participer à une conférence organisée par un utilisateur sur Internet  <br/> |Le client est sur Internet et le serveur de conférence dans le cloud.  <br/> |Internet  <br/> |Internet  <br/> |[Utilisateur en ligne sur votre réseau rejoignant une conférence hébergée en ligne](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Rejoindre une conférence hébergée sur un serveur sur site d'une autre société  <br/> |Client sur votre réseau et serveur de conférence dans un centre de données tiers.  <br/> |Internet  <br/> |Internet  <br/> |Non applicable  <br/> |Étant donné que le serveur de conférence qui héberge la conférence se trouve sur le réseau sur site d'un autre client, aucune donnée ne passe par le cloud Microsoft.  <br/> |
|Appel RTC  <br/> |Client sur le réseau du client et serveurs du système téléphonique dans le cloud  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Utilisateur en ligne sur votre réseau rejoignant une conférence hébergée en ligne](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Appel RTC  <br/> |Client sur Internet et serveurs du système téléphonique dans le cloud  <br/> |Internet  <br/> |Internet  <br/> |Non applicable  <br/> |Le trafic de médias et le trafic de signalisation sont envoyés vers le centre de données Microsoft 365 ou Office 365. Étant donné que le point de terminaison du client se trouve sur Internet, toutes les données sont issues du centre de données Microsoft sur Internet (même si un serveur Edge en ligne est requis pour la connectivité).  <br/> |

> [!NOTE]
> ExpressRoute sera utilisé sur le chemin de médias d’un utilisateur situé sur le réseau d’entreprise vers un serveur Edge en ligne, mais ne sera pas utilisé si le serveur Edge pour le déploiement local d’un autre client est utilisé.

### <a name="call-flows-for-skype-for-business-hybrid"></a>Flux d'appels hybride pour Skype Entreprise

Les flux d’appels hybrides s’appliquent lorsque vous avez un déploiement Skype Entreprise comprenant au moins certains utilisateurs qui sont domicile sur site. Les flux d’appels dans cette section comprennent à la fois des conférences sur site et des appels D’égal à égal ou PSTN avec au moins un utilisateur sur site.

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Cas d'utilisation** <br/> |**Points de terminaison** <br/> |**Chemin de signalisation** <br/> |**Chemin de médias** <br/> |**Exemple de flux** <br/> |**Remarques** <br/> |
|Appel d'égal à égal  <br/> |Deux clients, tous les deux sur le réseau du client et domiciliés sur site.  <br/> |Local  <br/> |local  <br/> |[Appel d’égal à égal pour un utilisateur Microsoft 365 ou Office 365 au sein du réseau du client](call-flow-using-expressroute.md#bk_Figure2) <br/> |Étant donné que les utilisateurs sont résident sur site, le trafic de signalisation est envoyé vers le centre de données sur site plutôt que vers le cloud.  <br/> |
|Appel d'égal à égal  <br/> |Deux clients, se connectant tous les deux depuis le réseau du client. L'un d'entre eux est domicilié en ligne, l'autre est domicilié sur site.  <br/> |Utilisateur en ligne : ExpressRoute  <br/> Utilisateur sur site : local  <br/> |local  <br/> |[Appel d’égal à égal pour les utilisateurs de Microsoft 365 ou Office 365 au sein du réseau du client](call-flow-using-expressroute.md#bk_Figure2) <br/> |Seul l’utilisateur homed en ligne envoie le trafic de signalisation vers le cloud.  <br/> |
|Appel d'égal à égal vers un utilisateur dans une organisation fédérée  <br/> |Deux clients, un utilisateur sur site sur le réseau du client (interne) et un utilisateur en ligne sur le réseau de la société fédérée (fédéré).  <br/> |Utilisateur interne : local  <br/> Utilisateur fédéré : ExpressRoute  <br/> |Internet ou ExpressRoute (selon si un serveur Edge en ligne ou sur site est utilisé)  <br/> |[Utilisateur en ligne](call-flow-using-expressroute.md#bk_Figure3) sur votre réseau rejoignant une conférence hébergée en ligne et faisant partie du serveur Edge sur site avec [les conférences hébergées sur Microsoft 365 ou Office 365](call-flow-using-expressroute.md#bk_Figure5) (pour le trafic de médias). <br/> |Suppose qu’un pare-feu bloque les connexions directes entre les clients, serveur Edge en ligne. La négociation ICE permettra une connectivité à la fois par des serveurs Edge en ligne (par l’utilisateur en ligne) et sur site (par l’utilisateur sur site).  <br/> |
|Rejoindre une conférence organisée par un utilisateur sur le réseau du client (conférence organisée par un utilisateur en ligne).  <br/> |Utilisateur sur site sur votre réseau et serveur de conférence dans le cloud.  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Utilisateur en ligne sur votre réseau rejoignant une conférence hébergée en ligne](call-flow-using-expressroute.md#bk_Figure3) <br/> |Les ressources serveur pour une conférence téléphonique sont définies par l’organisateur de la réunion. Dans ce cas, il a été programmé par un utilisateur en ligne, les ressources sont donc dans le cloud.  <br/> |
|Appel RTC  <br/> |Utilisateur sur site sur votre réseau et centre de données Skype Entreprise sur site.  <br/> |Local  <br/> |Local  <br/> |[Appel RTC utilisant Skype Entreprise version Cloud Connector](call-flow-using-expressroute.md#bk_Figure6) <br/> |Scénario similaire à l'utilisation de la version Cloud Connector, sauf que l'utilisateur est domicilié sur site, le trafic de signalisation ne sort donc pas de votre réseau.  <br/> |

### <a name="call-flows-for-skype-for-business-with-cloud-connector"></a>Flux d'appels pour Skype Entreprise avec Cloud Connector

Les utilisateurs qui se connectent à la version Cloud Connector sont tous domiciliés en ligne. Cela signifie que les conférences seront en ligne, et que le trafic de signalisation suivra les mêmes modèles que pour les utilisateurs en ligne. Pour les scénarios autres que les appels RTC, le flux d'appels sera exactement identique au flux décrit ci-dessus pour Skype Entreprise Online.

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Cas d'utilisation** <br/> |**Points de terminaison** <br/> |**Chemin de signalisation** <br/> |**Chemin de médias** <br/> |**Exemple de flux** <br/> |**Remarques** <br/> |
|Appel RTC  <br/> |Utilisateur en ligne sur votre réseau utilisant la version Cloud Connector.  <br/> |local  <br/> |local  <br/> |[Appel RTC utilisant Skype Entreprise version Cloud Connector](call-flow-using-expressroute.md#bk_Figure6) <br/> ||
|Appel RTC  <br/> |Utilisateur en ligne sur Internet utilisant la version Cloud Connector.  <br/> |Internet  <br/> |Internet  <br/> |Combinaison de serveur Edge sur site avec des [conférences hébergées sur Microsoft 365 ou Office 365](call-flow-using-expressroute.md#bk_Figure5) et d’appels [PSTN](call-flow-using-expressroute.md#bk_Figure6)à l’aide de Skype Entreprise, édition Cloud Connector.  <br/> |Les utilisateurs sur Internet se connecteront via le serveur Edge inclus dans Cloud Connector, et Cloud Connector se connectera au réseau RTC.  <br/> |

## <a name="related-topics"></a>Sujets associés

[Documentation ExpressRoute](https://go.microsoft.com/fwlink/?LinkId=690285)


