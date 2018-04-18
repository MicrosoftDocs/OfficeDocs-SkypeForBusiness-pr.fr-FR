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
ms.openlocfilehash: f74ea2376ed790e960b0b7a7cee00c05486ed11e
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/18/2018
---
# <a name="call-flow-using-expressroute"></a>Flux d'appels avec ExpressRoute

Cet article décrit les principes du flux d'appels pour Skype Entreprise Online et ExpressRoute, et vous présente des exemples détaillés de flux d'appels afin de vous permettre de comprendre et de planifier correctement.
  
Si vous déployez Skype pour entreprise en ligne dans le cadre d’Office 365, Skype pour Business Server hybride ou Skype pour connecteur de Cloud Business Edition, vous devez comprendre la communication entre le Skype pour les serveurs et les clients de l’entreprise et le flux d’appels donc Vous pouvez efficacement planifier, déployer, fonctionner et dépanner votre Skype pour les services professionnels en ligne. 
  
## <a name="call-flow-overview"></a>Présentation du flux d'appels

Ce document décrit le réseau les segments qui peuvent comporter des données pour l’appel de ces flux et vous aide à comprendre le trafic qui restera locales à votre réseau par rapport au trafic qui sera transmis via Internet ou par l’intermédiaire de ExpressRoute. Connaître le trafic qui utilise ExpressRoute vous aidera à évaluer les avantages que votre société reçoit à l’aide de ExpressRoute, mais aussi vous aident à que comprendre les instructions de déploiement ExpressRoute de valider et de résoudre les problèmes une fois que vous avez décidé de votre déploiement Pour utiliser ExpressRoute.
  
Les flux d'appels décrits ici peuvent être influencés par différents facteurs dont vous avez la maîtrise, tels que les règles de pare-feu, la configuration NAT, les proxys et la configuration du routeur. Ce document suppose que les paramètres recommandés ont été appliqués. Ces paramètres recommandés sont décrits dans les sections suivantes :
  
- [Configurer Skype Entreprise Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
    
- [URL et plages d'adresses IP Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
    
- [Vue d’ensemble de ExpressRoute](https://docs.microsoft.com/azure/expressroute/expressroute-introduction)
    
- [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/)
    
Le programme d’installation et les configurations qui n’ont pas suivi les étapes de l’installation de la documentation ci-dessus peuvent avoir des flux d’appel différent que celles que nous avons détaillés ici. En outre, vous pouvez constater vous-même avec les problèmes de configuration des itinéraires réseau asymétrique et non optimal, les protocoles de transport non optimales. Le routage asymétrique est un facteur important lorsque ExpressRoute est impliqué, car la ExpressRoute présente un second tracé à Office 365, qui crée la possibilité pour un itinéraire qui utilise Internet dans un sens et un autre itinéraire qui utilise ExpressRoute dans l’autre direction. Cela peut entraîner le trafic bloqué dans le sens de retour si elle traverse un pare-feu avec état.
  
## <a name="network-segments-and-traffic-types"></a>Segments réseau et types de trafic

### <a name="network-segments"></a>Segments réseau

Avant de pouvoir décrire les flux d'appels, il est important de définir certains termes afin que vous puissiez comprendre les segments réseau et les types de médias utilisés dans Skype Entreprise Online. 
  
Les diagrammes de flux d’appel ci-dessous vous indiquent quatre segments de réseau différents, chacun d'entre eux sont gérés par des organisations différentes (votre réseau interne, votre fournisseur de services réseau et leurs partenaires Internet et Microsoft) avec différentes caractéristiques de performances. Pour connaître les instructions sur les cibles de performances réseau, reportez-vous à [média qualité et les performances de connectivité réseau dans Skype pour l’activité en ligne](media-quality-and-network-connectivity-performance.md).
  
Vous pouvez voir ci-dessous chacun des segments réseau que nous allons aborder.
  
![Call Flow Network Segments.](../images/25689bf2-4753-4bea-b8d7-88dc8b6d2e2a.png)
  
 **Votre réseau** C’est le segment de réseau qui fait partie de votre réseau global que vous pouvez contrôler et gérer. Cela inclut toutes les connexions au sein de vos bureaux, filaire ou sans fil, entre des immeubles de bureaux, aux locaux de centres de données et vos connexions à des fournisseurs Internet ou les partenaires ExpressRoute.
  
En règle générale, la périphérie de votre réseau a un ou plusieurs DMZ avec des pare-feux ou des serveurs proxy, qui appliquent des stratégies de sécurité de votre organisation et qui permettent uniquement de certains trafics réseau que vous avez installé et configuré. Car vous gérez ce réseau, vous avez un contrôle direct sur les performances de votre réseau et il est fortement recommandé que vous effectuez les évaluations de réseau pour vérifier les performances à la fois dans les sites de votre réseau et de votre réseau à Skype pour les entreprises En ligne. Pour prendre connaissance des exigences en matière de performances, reportez-vous à la rubrique [Qualité des médias et performances de connectivité réseau dans Skype Entreprise Online](media-quality-and-network-connectivity-performance.md).
  
 **Internet** C’est le segment de réseau qui fait partie de votre réseau global qui sera utilisé par les utilisateurs qui sont connectent à Skype pour entreprise en ligne à partir de hors de votre réseau et sont utilisées pour toutes les connexions lorsque ExpressRoute n’est pas configuré. Internet et toutes les connexions ne sont pas gérés par vous ou Microsoft, afin que les performances et les chemins de routage ne peut pas être déterminés, et cela aura le plus grand impact sur le flux des appels et la qualité globale.
  
 **ExpressRoute** Il s'agit du segment réseau qui fait partie de votre réseau global et vous permet d'établir une connexion dédiée privée au réseau Microsoft. C’est l’option recommandée pour la connexion de votre réseau pour le réseau de Microsoft (Office 365 de centres de données) pour toutes les charges de travail dépendent de la vitesse du réseau et les performances, notamment Skype en ligne Business communication en temps réel. ExpressRoute les connexions sont effectuées entre votre réseau et de l’utilisation du réseau Microsoft [fournisseurs de connectivité ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-locations/) pour fournir un réseau privé et géré, avec prise en charge de la qualité de Service (QoS) qui peut améliorer les performances et de disponibilité de 99,9 % pour le multimédia en temps réel pendant les périodes de congestion du réseau.
  
 **Réseau Microsoft** Il s'agit du segment réseau qui fait partie du réseau global qui prend en charge les services Office 365. Ces services comprennent l'ensemble des communications entre les serveurs en ligne pour Office 365. Il peut s’agir du trafic qui traverse le réseau principal de Microsoft et est transmis entre les régions géographiques.
  
### <a name="types-of-traffic"></a>Types de trafic

Le trafic réseau pour Skype pour Business Online se divise en deux grandes catégories, comme des chemins d’accès distincts dans le flux d’appel :
  
 **Multimédia en temps réel** est encapsulées dans le protocole RTP (Real-Time Transport Protocol) de données et prend en charge les données audio, vidéo, partage d’applications et charges de transfert de fichier. En règle générale, le trafic multimédia étant hautement sensible, la latence vous pourriez ce trafic à prendre le chemin le plus direct possible, et pour utiliser UDP comme protocole de couche transport, car l’utilisation de TCP présente une latence plus élevée.
  
 **Signalisation** est la liaison de communication entre le client et le serveur, ou autres clients qui sont utilisés pour contrôler les activités (par exemple, lorsqu’un appel est initié) et proposer IMs. La majorité du trafic de signalisation utilise le protocole SIP, bien que certains clients utilisent des interfaces REST basées sur HTTP. Pour simplifier, nous envisageons une variété de signalisation qui peuvent transiter via les connexions HTTP et HTTPS ou TLS dans ce type de trafic. Il est important de comprendre que ce trafic est bien moins sensible à la latence, mais qu'il peut entraîner des indisponibilités de service ou des expirations de délai d'appel si la latence entre les points de terminaison excède plusieurs secondes.
  
Les destinations de ce trafic sont indiquées dans la section [URL et plages d'adresses IP Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) pour tous les services Office 365. Pour chaque URL, il est indiqué si la portion du trafic est susceptible de traverser ExpressRoute pour Office 365. Pour les diagrammes qui montrent que l’Internet est toujours utilisé pour certains types de trafic lorsque ExpressRoute est activé, consultez [ExpressRoute Azure pour Office 365](http://support.office.com/article/6d2534a2-c19c-4a99-be5e-33a0cee5d3bd). Il est important de comprendre que même des URL qui sont répertoriées comme étant routables sur ExpressRoute sont également routables sur Internet. Cela signifie que dans certains scénarios, la décision si Internet ou ExpressRoute sera utilisé dépend de l’emplacement du client et la configuration de serveurs proxy et de pare-feu. Il est également important de comprendre que depuis pas toutes les URL associées à Office 365 sont en mesure d’utiliser ExpressRoute, une connexion Internet est requise même si vous ExpressRoute d’achat auprès d’un partenaire ExpressRoute. 
  
Le trafic qui ne peut être envoyé via Internet comprend des dépendances Internet courantes, telles que les listes de révocation de certificats (CRL), les recherches DNS et la résolution de noms, les adresses URL pour les services partagés Office 365, comme pour le centre d’administration Office 365 et certaines non en temps réel fonctionnalités de communication de Skype pour Business Online, par exemple de télémétrie et de fédération pour l’interopérabilité avec Skype, consommateur, en tant que support bien qui est diffusé en continu pour la diffusion de réunion Skype. Afin de faciliter vos prises de décisions, reportez-vous à la section [Acheminement avec ExpressRoute pour Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408) pour obtenir davantage de détails en vue de la planification du routage de votre réseau.
  
## <a name="principles-for-call-flows-with-skype-for-business"></a>Principes du flux d'appels avec Skype Entreprise

Avant d'étudier en détails les scénarios de flux d'appels spécifiques, il existe six principes généraux qui vous permettent de comprendre les flux d'appels pour Skype Entreprise.
  
1. Un Skype pour des conférences professionnelles est hébergé dans la même région où l’organisateur de la conférence est hébergé. Cela s'applique au cloud Office 365 si l'organisateur est un utilisateur en ligne, ou à un centre de données sur site si l'organisateur de la réunion est un utilisateur sur site.
    
2. Trafic de Media envoyé par un client à une conférence hébergée toujours acheminée vers le serveur hébergeant la conférence. Cela peut être un serveur local au sein d’un centre de données que vous gérez ou un serveur en ligne dans le nuage d’Office 365. Toutefois, un serveur Edge est toujours utilisé pour les flux multimédias de conférences en ligne.
    
3. Le trafic de médias pour les appels d'égal à égal emprunte la route la plus directe disponible. La route préférée est la route directe jusqu'à l'homologue distant (client). Si toutefois cette route n'est pas disponible en raison du blocage du trafic par le pare-feu ou d'une raison similaire, un ou plusieurs serveurs Edge relaient alors le trafic.
    
4. Le trafic de signalisation est toujours acheminé vers le serveur sur lequel l'utilisateur est domicilié, c'est-à-dire en ligne ou sur site. Un serveur Edge sera utilisé s'il est impossible d'établir une connexion directe au serveur frontal.
    
5. Les utilisateurs qui rejoignent une conférence hébergée en ligne utiliseront toujours un serveur Edge (ou deux si les configurations de pare-feu du client le nécessitent).
    
6. Les utilisateurs qui rejoignent une conférence hébergée sur site n'utiliseront généralement pas de serveur Edge s'ils se connectent depuis le même réseau contenant le déploiement sur site, et ils utiliseront un ou deux serveurs Edge lorsqu'ils se connectent depuis l'extérieur de votre réseau. 
    
Pour obtenir davantage de détails sur la sélection du chemin emprunté par les médias, veuillez vous reporter à la rubrique [ICE - Connectivité Edge des médias](https://aka.ms/AVEdge). Bien que cette vidéo traite de Lync Server 2013, les principes et les protocoles s’appliquent toujours à Skype pour les entreprises.
  
## <a name="skype-for-business-call-flows-with-expressroute"></a>Flux d'appels Skype Entreprise avec ExpressRoute

Maintenant que vous avez comprendre les quatre segments de réseau différents et certains principes directeurs généraux pour Skype pour les flux d’appel de professionnels, vous pouvez utiliser que les informations qui vous aideront à comprendre le Skype pour le trafic d’entreprise seront parcourir un ExpressRoute segment de réseau.
  
En règle générale, le trafic réseau traverse la connexion ExpressRoute si l'un des points de terminaison se trouve dans votre réseau et si l'autre point de terminaison se trouve dans le centre de données Office 365. Ce trafic comprend le trafic de signalisation entre le client et le serveur, le trafic de médias utilisé lors des téléconférences, ou les appels d'égal à égal qui utilisent un serveur Edge en ligne.
  
Le trafic ne traversera pas la connexion ExpressRoute si les deux points de terminaison sont en mesure de communiquer directement sur Internet ou s'ils sont tous les deux situés dans votre réseau. Cela inclura des media pour les appels de peer-to-peer, le trafic Internet destiné à un déploiement sur site ou tout le trafic entre Internet et les serveurs de périphérie Office 365. À titre d'exemple, il peut s'agir du trafic d'un utilisateur rejoignant une conférence en ligne depuis un hôtel.
  
## <a name="basic-skype-for-business-call-flow"></a>Flux d'appel de base Skype Entreprise

Afin de vous aider à mettre en application les principes généraux des flux d'appels Skype Entreprise décrits plus haut, la section suivante de cet article comprend plusieurs diagrammes à des fins de référence. Il ne s'agit pas d'une liste exhaustive des différents flux d'appels existants mais d'une aide en vue de la mise en application des principes détaillés plus haut. En outre, les scénarios décrits dans les diagrammes ont été sélectionnés pour couvrir les types de déploiement courants, notamment en ligne, hybrides, Cloud Connector et dans le cas particulier de la diffusion de réunion Skype.
  
> [!NOTE]
> Un sous-ensemble de trafic utilisé par Skype pour entreprise n’est pas routable sur ExpressRoute et prendra toujours un chemin d’accès Internet. Reportez-vous à l' [Office 365 URL et les plages d’adresses IP](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) pour déterminer les URL qui peuvent être affectées.
  
### <a name="peer-to-peer-call-for-office-365-users-from-within-customer-network"></a>Appel de peer-to-peer pour les utilisateurs de Office 365 au sein du réseau client
<a name="bk_Figure2"> </a>

Pour les appels d'égal à égal, le trafic de médias emprunte toujours la route la plus directe pour parvenir à destination. Toutefois, le trafic de signalisation est acheminé jusqu'au centre de données Office 365 dans lequel l'utilisateur en ligne est domicilié. Étant donné que les deux utilisateurs se trouvent sur le même WAN et que rien n'empêche les clients de communiquer directement, les médias sont acheminés directement entre les deux clients. Le trafic de signalisation, pour les deux utilisateurs, traverse la connexion ExpressRoute destinée au centre de données de chaque organisation. Pour afficher le flux d'appels dans ce scénario, reportez-vous au document suivant.
  
 **Flux d'appels d'égal à égal**
  
![Call Flow with Peer to Peer call.](../images/f460369e-bfce-4a03-a031-d7e92c4ace89.png)
  
### <a name="online-user-on-your-network-joining-a-conference-that-is-hosted-online"></a>Utilisateur en ligne sur votre réseau rejoignant une conférence hébergée en ligne
<a name="bk_Figure3"> </a>

Dans l’exemple de peer-to-peer, le trafic multimédia prend toujours l’itinéraire le plus direct vers sa destination. Toutefois, pour une conférence en ligne, la destination est dans le nuage d’Office 365. Cela signifie que le trafic de médias de tous les utilisateurs rejoignant la conférence depuis votre réseau traverse la connexion ExpressRoute et que le trafic de signalisation est acheminé jusqu'au cloud Office 365. L’illustration ci-dessous vous montre que le système d’exploitation ne parcourent pas la connexion ExpressRoute d’un utilisateur au sein de votre réseau et du support de signalisation et qu’il va parcourir directement par les utilisateurs qui sont connectés à Internet à partir de l’extérieur de votre réseau, comme dans un café Internet usine ou un hôtel.
  
N’oubliez pas que l’emplacement d’une conférence est définie par l’organisateur de la réunion et non par les participants. Cela signifie que si la réunion a été planifiée par un client local, le trafic multimédia ne sont pas déborder vers le nuage Office 365 ExpressRoute, mais plutôt traversent l’Internet au centre de données sur site de l’organisateur de la réunion.
  
La destination des médias pour une conférence en ligne sera un centre de données dans le cloud Office 365, le centre de données pouvant toutefois se trouver dans une région géographique différente de celles des utilisateurs qui rejoignent la conférence. Cette situation peut se produire dans deux cas :
  
- Si l'organisateur de la réunion travaille pour une société différente de celle des participants, et si l'organisation de l'organisateur est hébergée dans une région géographique ou un pays différent
    
- Si un utilisateur rejoint la réunion depuis une région ou un pays différent de la région ou du pays de l'organisation de la société, soit parce que la société est une multinationale, soit parce que l'utilisateur est en déplacement
    
La bonne nouvelle à propos de l’utilisation de ExpressRoute dans ce scénario est qu’avec ExpressRoute complémentaire, les données qui suit le chemin d’accès ExpressRoute passera automatiquement sur la dorsale de Microsoft quelle que soit la région géographique de l’organisateur de la réunion Centre de données de l’organisation.
  
 **Flux d'appels d'un utilisateur en ligne pour une réunion en ligne**
  
![Call flow for an online hosted conference call.](../images/22d9ee64-b20c-4079-b3d1-a7a806b9a0bc.png)
  
### <a name="joining-a-conference-hosted-by-on-premises-user-in-hybrid-deployment"></a>Rejoindre une conférence hébergée par un utilisateur sur site dans un déploiement hybride
<a name="bk_Figure3"> </a>

N’oubliez pas que les serveurs de conférence qui prennent en charge les conférences hébergées sont déterminées par où l’organisateur de la réunion est hébergé. Dans ce scénario, support pour tous les utilisateurs, participation à une conférence planifiée par un utilisateur local dans un déploiement hybride passera à un centre de données sur site. Signalisation pour utilisateurs hébergées en ligne est établie par l’intermédiaire de leur organisation dans le nuage Office 365, tandis que les media tentera une connexion directe. Dans ce scénario, dans la mesure où les utilisateurs sont connectent à partir de votre réseau, une connexion media direct est possible, ExpressRoute est utilisé uniquement pour la signalisation de trafic pour l’utilisateur hébergée en ligne. Si un utilisateur hébergée en ligne se connecte à partir d’Internet, le support peut traverser ExpressRoute si un serveur Edge en ligne permet de se connecter.
  
 **Flux d'appels d'une conférence hébergée par un utilisateur hybride**
  
![Call flow hosted onprem.](../images/9e669859-19f3-4a86-95b7-7185eb421ccd.png)
  
### <a name="on-premises-edge-server-with-office-365-hosted-conferences"></a>Serveur Edge sur site avec conférences hébergées sur Office 365
<a name="bk_Figure5"> </a>

Lorsqu’un utilisateur les jointures hybride en ligne hébergé de conférence, nous savons que de signalisation et de media est destiné le nuage d’Office 365, et dans la mesure où l’utilisateur va se joindre à partir d’Internet, normalement un chemin d’accès internet direct serait à prendre. Toutefois, dans certains cas, par exemple en raison de restrictions de pare-feu, un chemin d’accès Internet direct n’est pas disponible. Dans ce cas, un serveur de transport Edge sur site peut relayer le trafic multimédia, qui provoque le trafic multimédia revenir à votre réseau local avant d’entamer le circuit ExpressRoute le nuage d’Office 365.
  
 **Utilisateur sur site rejoignant une téléconférence en ligne à l'aide d'un serveur Edge sur site**
  
![Call flow for a conference call going through an edge server.](../images/0178c170-5837-430d-84f1-582784bfef55.png)
  
### <a name="pstn-call-using-skype-for-business-cloud-connector-edition"></a>Appel RTC utilisant Skype Entreprise version Cloud Connector
<a name="bk_Figure6"> </a>

L'utilisation de [Skype Entreprise Online version Cloud Connector](https://aka.ms/CloudConnectorInstaller) offre une connectivité RTC grâce aux ressources sur site telles qu'une jonction SIP ou une passerelle RTC, ou en ayant recours à du matériel léger pour l'intégration avec Skype Entreprise. Avec l’édition du connecteur de nuage, les utilisateurs sont hébergées en ligne et agissent comme des utilisateurs en ligne normales lorsqu’ils n’incluent pas de Plans d’appel. Dans le cadre des appels RTC, le trafic de signalisation est acheminé du client au Cloud au moyen d'une connexion ExpressRoute, si disponible, et le trafic de médias ne sort pas de votre WAN. Dans ce cas, le trafic de signalisation est réacheminé vers le cloud Office 365 jusqu'à atteindre le Cloud Connector.
  
 **Appels RTPC via le système téléphonique dans Office 365 et connecteur de nuage**
  
![Call flow for a PSTN call using Cloud PBX Cloud Connector.](../images/e48d0f2b-fa1e-4b43-b3dd-d34a33dcdf36.png)
  
### <a name="skype-meeting-broadcast-with-users-joining-from-customer-network"></a>Diffusion de réunion Skype avec des utilisateurs se connectant depuis le réseau du client
<a name="bk_Figure6"> </a>

La diffusion de réunion Skype est un cas d'utilisation particulier, il s'agit d'une réunion en deux parties, chaque partie présentant un profil de transport réseau différent. La première partie et celui qui est le plus important à partir d’un réseau point de vue des performances, est la réunion interne. Il s’agit de la partie en temps réel de la réunion qui inclut un ou plusieurs points de terminaison client connexion du serveur de conférence dans le nuage d’Office 365. Les données transmises à l’aide de cette partie de la réunion sont exactement comme dans l’exemple ci-dessus, avec une jonction d’utilisateur Office 365 et de la conférence en ligne. 
  
Diffusion de réunion Skype unique le fait que la réunion est distribuée à un grand nombre de participants à la conférence à l’aide d’une diffusion en flux continu du service. Cette diffusion en flux continu de service n’est pas routable sur ExpressRoute, mais utilise à la place d’Internet avec la prise en charge facultative des services de réseau CDN (Content Delivery). Il est important de reconnaître que la diffusion en flux continu est un flux unidirectionnel de média car les participants écoutent mais ne parlez pas et prend en charge la mise en mémoire tampon, afin qu’il soit beaucoup moins sensible aux problèmes de performances réseau comme la gigue, perte de paquets et la latence. Au lieu d’optimiser le trafic de diffusion de ces problèmes, il est optimisé pour l’utilisation de la bande passante, car il existe potentiellement un très grand nombre de participants de recevoir les flux multimédias.
  
 **Diffusion de réunion Skype avec des utilisateurs depuis le réseau du client**
  
![Call flow for Skype Meeting Broadcast.](../images/cbe0e9f3-7eee-47e9-b61e-f2780b525dea.png)
  
## <a name="call-flow-patterns-by-deployment-type"></a>Modèles de flux d'appels par type de déploiement

Avec le courant d’appel exemples de flux ci-dessus, et comprendre les principes généraux qui contrôlent le trafic, les tableaux ci-dessous fournissent un résumé des modèles de trafic pour une combinaison de grande taille des scénarios de déploiement et d’utilisation. Ces tableaux ne couvrent pas l'intégralité des combinaisons de flux d'appels possibles, mais ils devraient vous aider à comprendre davantage les principes généraux des flux d'appels.
  
Données transmises et répertoriées comme étant des locaux de l’organisation ; Il ne quitte pas le client réseau, Internet ou ExpressRoute. Les modèles répertoriés ci-dessous sont basés sur les paramètres de réseau plus courantes, telles que les pare-feux, la fédération et Internet et supposent que toutes les organisations impliquées dans des flux multiples tiers ou fédérés sont ExpressRoute. En pratique, avec d'autres paramètres, les modèles de trafic peuvent être différents de ceux répertoriés ci-dessous.
  
### <a name="call-flows-for-skype-for-business-online"></a>Flux d'appels pour Skype Entreprise Online

Skype pour les scénarios d’utilisation en ligne Business impliquent des utilisateurs qui sont hébergées en ligne et qui peuvent appeler à partir d’Internet ou de votre réseau interne. Des serveurs sur site ne faisant pas partie de ces scénarios, afin que toutes les conférences ou média associé de RTPC se déplacera vers le nuage d’Office 365 et les utilisateurs en ligne serveur Edge sera également dans le nuage.
  
 **Flux d'appels résumé pour Skype Entreprise Online**
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Cas d'utilisation** <br/> |**Points de terminaison** <br/> |**Chemin de signalisation** <br/> |**Chemin de médias** <br/> |**Exemple de flux** <br/> |**Remarques** <br/> |
|Appel d'égal à égal  <br/> |Deux clients, tous les deux sur votre réseau.  <br/> |ExpressRoute  <br/> |local  <br/> |[Appel de peer-to-peer pour les utilisateurs de Office 365 au sein du réseau client](call-flow-using-expressroute.md#bk_Figure2) <br/> ||
|Appel d'égal à égal  <br/> |Deux clients, sur votre réseau (interne) et l’autre client sur Internet (externe).  <br/> |Utilisateur interne : ExpressRoute  <br/> Utilisateur externe : Internet  <br/> |Utilisateur interne : ExpressRoute  <br/> Utilisateur externe : Internet vers serveur Edge Office 365.  <br/> |[Appel de peer-to-peer pour les utilisateurs de Office 365 au sein du réseau client](call-flow-using-expressroute.md#bk_Figure2) <br/> |Suppose que le pare-feu bloque les connexions directes entre les clients, ce qui nécessite un serveur Edge en ligne. Le trafic utilisateur interne vers le serveur de transport Edge en ligne suit le chemin d’accès similaire, que, pour le serveur de conférence pour la téléconférence.  <br/> |
|Appel d'égal à égal vers un utilisateur dans une organisation fédérée  <br/> |Deux clients, un sur votre réseau (interne) et un utilisateur en ligne sur le réseau de l'organisation fédérée (fédéré).  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Utilisateur en ligne sur votre réseau rejoignant une conférence hébergée en ligne](call-flow-using-expressroute.md#bk_Figure3) <br/> |Suppose qu'un pare-feu bloque les connexions directes entre les clients, serveur Edge en ligne requis. Le trafic provenant de l'utilisateur interne à destination du serveur Edge en ligne suit un chemin similaire à celui d'un serveur de conférence pour une téléconférence.  <br/> |
|Rejoindre une téléconférence organisée par un utilisateur sur le réseau du client  <br/> |Client sur votre réseau et serveur de conférence dans le cloud Office 365.  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Utilisateur en ligne sur votre réseau rejoignant une conférence hébergée en ligne](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Joindre la téléconférence par utilisateur dans Internet  <br/> |Client réside sur le serveur Internet et de la conférence dans le nuage d’Office 365.  <br/> |Internet  <br/> |Internet  <br/> |[Utilisateur en ligne sur votre réseau rejoignant une conférence hébergée en ligne](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Rejoindre une conférence hébergée sur un serveur sur site d'une autre société  <br/> |Client sur votre réseau et serveur de conférence dans un centre de données tiers.  <br/> |Internet  <br/> |Internet  <br/> |Non applicable  <br/> |Étant donné que le serveur de conférence qui héberge la conférence se trouve sur le réseau sur site d'un autre client, aucune donnée ne passe par le cloud Microsoft.  <br/> |
|Appel RTC  <br/> |Client dans un réseau client et les serveurs de système téléphonique dans le nuage d’Office 365  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Utilisateur en ligne sur votre réseau rejoignant une conférence hébergée en ligne](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Appel RTC  <br/> |Client sur les serveurs Internet et le système téléphonique de nuage d’Office 365  <br/> |Internet  <br/> |Internet  <br/> |Non applicable  <br/> |Le support et la signalisation sera circulent vers le centre de données d’Office 365. Dans la mesure où le point de terminaison de client se trouve sur Internet, tous les flux de données au centre de données Microsoft sur Internet (même si un serveur Edge en ligne est nécessaire pour la connexion).  <br/> |
   
> [!NOTE]
> ExpressRoute sera utilisé sur le chemin d’accès du support d’un utilisateur sur le réseau d’entreprise à un serveur de transport Edge en ligne, mais ne seront pas utilisé si le serveur de transport Edge pour un déploiement sur site d’un autre client est utilisé. 
  
### <a name="call-flows-for-skype-for-business-hybrid"></a>Flux d'appels hybride pour Skype Entreprise

Les flux d'appels hybrides sont utilisés lorsque vous disposez d'un déploiement Skype Entreprise comprenant au moins plusieurs utilisateurs domiciliés sur site. Les flux d’appel dans cette section incluent les deux conférences sur site et peer-to-peer ou RTC appelle au moins un utilisateur hébergées sur site.
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Cas d'utilisation** <br/> |**Points de terminaison** <br/> |**Chemin de signalisation** <br/> |**Chemin de médias** <br/> |**Exemple de flux** <br/> |**Remarques** <br/> |
|Appel d'égal à égal  <br/> |Deux clients, tous les deux sur le réseau du client et domiciliés sur site.  <br/> |Local  <br/> |local  <br/> |[Appel de peer-to-peer pour les utilisateurs de Office 365 au sein du réseau client](call-flow-using-expressroute.md#bk_Figure2) <br/> |Étant donné que les utilisateurs sont domiciliés sur site, le trafic de signalisation est acheminé vers le centre de données sur site et non vers le cloud Office 365.  <br/> |
|Appel d'égal à égal  <br/> |Deux clients, se connectant tous les deux depuis le réseau du client. L'un d'entre eux est domicilié en ligne, l'autre est domicilié sur site.  <br/> |Utilisateur en ligne : ExpressRoute  <br/> Utilisateur sur site : local  <br/> |local  <br/> |[Appel de peer-to-peer pour les utilisateurs de Office 365 au sein du réseau client](call-flow-using-expressroute.md#bk_Figure2) <br/> |Seul l'utilisateur domicilié en ligne envoie le trafic de signalisation au cloud Office 365.  <br/> |
|Appel d'égal à égal vers un utilisateur dans une organisation fédérée  <br/> |Deux clients, un utilisateur sur site sur le réseau du client (interne) et un utilisateur en ligne sur le réseau de la société fédérée (fédéré).  <br/> |Utilisateur interne : local  <br/> Utilisateur fédéré : ExpressRoute  <br/> |Internet ou ExpressRoute (selon si un serveur Edge en ligne ou sur site est utilisé)  <br/> |[L’utilisateur en ligne sur votre réseau de participation à une conférence qui est hébergé en ligne](call-flow-using-expressroute.md#bk_Figure3) et une partie de [serveur local bord avec Office 365 hébergé conférences](call-flow-using-expressroute.md#bk_Figure5) (pour le trafic de média). <br/> |Suppose qu’un pare-feu bloque les connexions directes entre les clients, que le serveur de transport Edge en ligne. Négociation de glace propose à la fois en ligne (par l’utilisateur en ligne) et les serveurs de périphérie local (par l’utilisateur local) pour la connectivité.  <br/> |
|Rejoindre une conférence organisée par un utilisateur sur le réseau du client (conférence organisée par un utilisateur en ligne).  <br/> |Client sur site sur votre réseau et serveur de conférence dans le cloud Office 365.  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Utilisateur en ligne sur votre réseau rejoignant une conférence hébergée en ligne](call-flow-using-expressroute.md#bk_Figure3) <br/> |Ressources du serveur de conférence téléphonique sont définies par l’organisateur de la réunion. Dans ce cas, la réunion a été organisée par un utilisateur en ligne, les ressources sont par conséquent dans le cloud Office 365.  <br/> |
|Appel RTC  <br/> |Utilisateur sur site sur votre réseau et centre de données Skype Entreprise sur site.  <br/> |Local  <br/> |Local  <br/> |[Appel RTC utilisant Skype Entreprise version Cloud Connector](call-flow-using-expressroute.md#bk_Figure6) <br/> |Scénario similaire à l'utilisation de la version Cloud Connector, sauf que l'utilisateur est domicilié sur site, le trafic de signalisation ne sort donc pas de votre réseau.  <br/> |
   
### <a name="call-flows-for-skype-for-business-with-cloud-connector"></a>Flux d'appels pour Skype Entreprise avec Cloud Connector

Les utilisateurs qui se connectent à la version Cloud Connector sont tous domiciliés en ligne. Cela signifie que les conférences seront en ligne, et que le trafic de signalisation suivra les mêmes modèles que pour les utilisateurs en ligne. Pour les scénarios autres que les appels RTC, le flux d'appels sera exactement identique au flux décrit ci-dessus pour Skype Entreprise Online.
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Cas d'utilisation** <br/> |**Points de terminaison** <br/> |**Chemin de signalisation** <br/> |**Chemin de médias** <br/> |**Exemple de flux** <br/> |**Remarques** <br/> |
|Appel RTC  <br/> |Utilisateur en ligne sur votre réseau utilisant la version Cloud Connector.  <br/> |local  <br/> |local  <br/> |[Appel RTC utilisant Skype Entreprise version Cloud Connector](call-flow-using-expressroute.md#bk_Figure6) <br/> ||
|Appel RTC  <br/> |Utilisateur en ligne sur Internet utilisant la version Cloud Connector.  <br/> |Internet  <br/> |Internet  <br/> |Combinaison de [serveur local bord avec Office 365 hébergé des conférences](call-flow-using-expressroute.md#bk_Figure5) et [RTPC appeler à l’aide de Skype pour connecteur de Cloud Business Edition](call-flow-using-expressroute.md#bk_Figure6).  <br/> |Les utilisateurs sur Internet se connecteront via le serveur Edge inclus dans Cloud Connector, et Cloud Connector se connectera au réseau RTC.  <br/> |
   
## <a name="related-topics"></a>Rubriques connexes

[Documentation ExpressRoute](https://go.microsoft.com/fwlink/?LinkId=690285)

  
 