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
ms.openlocfilehash: 3c728dab868177aab07c6fe618fba3a8c357eaa2
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41706669"
---
# <a name="call-flow-using-expressroute"></a>Flux d'appels avec ExpressRoute

Cet article décrit les principes du flux d'appels pour Skype Entreprise Online et ExpressRoute, et vous présente des exemples détaillés de flux d'appels afin de vous permettre de comprendre et de planifier correctement.

Si vous déployez Skype entreprise Online dans le cadre d’Office 365, de Skype entreprise Server hybride ou de Skype entreprise version Cloud Connector, vous devrez comprendre la communication entre le client et les serveurs Skype entreprise et le flux d’appels. vous pouvez planifier, déployer, utiliser et dépanner efficacement vos services Skype entreprise online.

## <a name="call-flow-overview"></a>Présentation du flux d'appels

Ce document décrit les segments réseau qui peuvent transporter des données pour ces flux d’appels et vous permet de comprendre le trafic local de votre réseau par rapport au trafic qui transitera via Internet ou par le biais de ExpressRoute. Le fait de savoir quel est le trafic qui utilise ExpressRoute vous aidera à évaluer les avantages que votre entreprise recevra en utilisant ExpressRoute, ainsi que les instructions de déploiement d’ExpressRoute pour valider et dépanner votre déploiement une fois que vous avez décidé pour utiliser ExpressRoute.

Les flux d'appels décrits ici peuvent être influencés par différents facteurs dont vous avez la maîtrise, tels que les règles de pare-feu, la configuration NAT, les proxys et la configuration du routeur. Ce document suppose que les paramètres recommandés ont été appliqués. Ces paramètres recommandés sont décrits dans les sections suivantes :

- [Configurer Skype Entreprise Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

- [URL et plages d'adresses IP Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

- [Présentation de ExpressRoute](https://docs.microsoft.com/azure/expressroute/expressroute-introduction)

- [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/)

La configuration et les configurations qui n’ont pas été suivies dans la documentation ci-dessus peuvent avoir des flux d’appels différents de ceux que nous avons décrits ici. Par ailleurs, vous pouvez vous retrouver avec des problèmes de configuration tels que les itinéraires réseau asymétriques et non optimaux, ou les protocoles de transport non optimaux. Le routage asymétrique est une considération importante lorsque ExpressRoute est impliqué, car ExpressRoute introduit un deuxième chemin d’accès à Office 365, ce qui crée la possibilité d’un itinéraire qui utilise Internet dans une direction et un autre qui utilise ExpressRoute dans l’autre direction. Cela peut entraîner le blocage du trafic dans la direction de retour s’il traverse un pare-feu dynamique.

## <a name="network-segments-and-traffic-types"></a>Segments réseau et types de trafic

### <a name="network-segments"></a>Segments réseau

Avant de pouvoir décrire les flux d'appels, il est important de définir certains termes afin que vous puissiez comprendre les segments réseau et les types de médias utilisés dans Skype Entreprise Online.

Les diagrammes de flux d’appels ci-dessous présentent quatre segments réseau différents, chacun d’eux étant géré par différentes organisations (votre réseau interne, votre fournisseur de services réseau et leurs partenaires d’homologation Internet et Microsoft) qui présentent des caractéristiques de performance différentes. Pour obtenir des instructions sur les cibles de performance réseau, voir [qualité multimédia et performances de connectivité réseau dans Skype entreprise Online](media-quality-and-network-connectivity-performance.md).

Vous pouvez voir ci-dessous chacun des segments réseau que nous allons aborder.

![Call Flow Network Segments.](../images/25689bf2-4753-4bea-b8d7-88dc8b6d2e2a.png)

 **Votre réseau** Il s’agit du segment réseau qui fait partie de votre réseau global que vous contrôlez et gérez. Il s’agit de toutes vos connexions au sein de vos bureaux, qu’elles soient filaires ou sans fil, entre les bâtiments d’Office, les centres de donnes locaux et vos connexions aux fournisseurs de services Internet ou ExpressRoute.

En règle générale, le bord de votre réseau dispose d’une ou de plusieurs DMZ avec des pare-feu et/ou des serveurs proxy qui appliquent les stratégies de sécurité de votre organisation et autorisent uniquement le trafic réseau configuré et configuré. Dans la mesure où vous gérez ce réseau, vous disposez d’un contrôle direct sur les performances de votre réseau et il est vivement recommandé d’effectuer les évaluations réseau pour valider les performances des sites de votre réseau et de votre réseau à Skype entreprise online. Pour connaître la configuration requise en termes de performances, voir [qualité multimédia et performances de connectivité réseau dans Skype entreprise Online](media-quality-and-network-connectivity-performance.md).

 **Internet** Il s’agit du segment réseau qui fait partie de votre réseau global qui sera utilisé par les utilisateurs qui se connectent à Skype entreprise Online à partir de l’extérieur de votre réseau et qui est utilisé pour toutes les connexions lorsque ExpressRoute n’est pas configuré. Internet et toutes ses connexions ne sont pas gérés par vous ou Microsoft, de sorte que les performances et les chemins de routage ne peuvent pas être déterminés, et cela a un impact sur le débit global et la qualité des appels.

 **ExpressRoute** Il s’agit du segment réseau qui fait partie de votre réseau global et qui vous offrira une connexion privée et dédiée au réseau Microsoft. Il s’agit de l’option recommandée pour la connexion de votre réseau aux centres de données du réseau Microsoft (les centres de données Office 365), en fonction de la vitesse et des performances du réseau, telles que la communication en temps réel de Skype entreprise online. ExpressRoute connexions entre votre réseau et Microsoft Network utilise des fournisseurs de [connectivité ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-locations/) pour fournir un réseau privé et géré, avec une disponibilité de 99,9% et une prise en charge de la qualité de service (QoS) qui peut améliorer les performances en temps réel pendant les périodes de congestion du réseau.

 **Microsoft Network** Il s’agit du segment réseau qui fait partie de votre réseau global prenant en charge les services Office 365. Cela inclut toutes les communications entre les serveurs en ligne pour Office 365. Cela peut inclure le trafic qui traverse le réseau principal Microsoft et est transmis entre les régions géographiques.

### <a name="types-of-traffic"></a>Types de trafic

Le trafic réseau de Skype entreprise Online est réparti en deux grandes catégories, sous la forme de chemins distincts dans le flux d’appels :

 Les données **multimédias en temps réel** sont encapsulées au sein du protocole RTP (Real-Time Transport Protocol) et prennent en charge les charges de travail audio, vidéo, de partage d’application et de transfert de fichiers. En règle générale, le trafic multimédia est sensible à la latence, de telle sorte que vous souhaitez que ce trafic prenne le plus en chemin direct possible et utilise le protocole UDP comme protocole de couche de transport, car l’utilisation de TCP introduit une latence élevée.

 Le **signalement** est le lien de communication entre le client et le serveur ou d’autres clients qui sont utilisés pour contrôler les activités (par exemple, lorsqu’un appel est lancé) et livrer des messages instantanés. La plupart du trafic de signalisation utilise le protocole SIP, même si certains clients utilisent des interfaces REST basées sur HTTP. Pour le simplifier, nous envisageons un grand nombre de signalisation qui peuvent voyager sur des connexions HTTP et HTTPs ou TLS dans ce type de trafic. Il est important de comprendre que ce trafic est beaucoup plus sensible à la latence, mais peut entraîner des expirations de service ou des délais d’expiration de l’appel si la latence entre les points de terminaison excède plusieurs secondes.

Les destinations pour ce trafic se trouvent dans les [URL et plages d’adresses IP office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) pour tous les services Office 365. Pour chaque URL, il indique si cette partie du trafic risque de traverser le ExpressRoute pour Office 365. Pour les diagrammes montrant que l’Internet est toujours utilisé pour le trafic lorsque ExpressRoute est activé, voir [Azure ExpressRoute pour Office 365](https://support.office.com/article/6d2534a2-c19c-4a99-be5e-33a0cee5d3bd). Il est important de comprendre que même les URL qui sont répertoriées comme routables sur ExpressRoute sont également routables via Internet. Cela signifie que dans certains cas, la détermination de l’utilisation de l’Internet ou du ExpressRoute dépend de l’emplacement du client et de la configuration des serveurs proxy et des pare-feu. Il est également important de comprendre que dans la mesure où toutes les URL associées à Office 365 ne peuvent pas utiliser ExpressRoute, une connexion Internet est requise même si vous achetez ExpressRoute auprès d’un partenaire ExpressRoute.

Le trafic qui ne peut être envoyé qu’via Internet comporte des dépendances Internet communes. par exemple, les listes de révocation de certificats, les recherches DNS et la résolution de nom, les URL des services Office 365 partagés, comme le centre d’administration de Microsoft 365 et certaines fonctionnalités de communication non en temps réel de Skype entreprise Online, telles que la télémétrie et la Fédération pour l’interopérabilité avec les utilisateurs de Skype, ainsi que les éléments multimédias diffusés en continu pour la Pour vous aider à prendre des décisions, voir [routage avec ExpressRoute pour Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408) pour plus d’informations sur le routage de votre réseau.

## <a name="principles-for-call-flows-with-skype-for-business"></a>Principes du flux d'appels avec Skype Entreprise

Avant d'étudier en détails les scénarios de flux d'appels spécifiques, il existe six principes généraux qui vous permettent de comprendre les flux d'appels pour Skype Entreprise.

1. Une conférence Skype entreprise est hébergée dans la même région que celle de l’organisateur de la Conférence. Il s’agit du Cloud Office 365 si l’organisateur est un utilisateur en ligne ou dans un centre de donnees sur site si l’organisateur de la réunion est un utilisateur local.

2. Le trafic multimédia envoyé d’un client à une conférence hébergée est toujours transféré sur le serveur où la Conférence est hébergée. Il s’agit-il d’un serveur local au sein d’un centre de contenus géré ou d’un serveur en ligne dans le Cloud Office 365. Toutefois, un serveur Edge est toujours utilisé pour le flux multimédia pour les conférences en ligne.

3. Le trafic de médias pour les appels d'égal à égal emprunte la route la plus directe disponible. La route préférée est la route directe jusqu'à l'homologue distant (client). Si toutefois cette route n'est pas disponible en raison du blocage du trafic par le pare-feu ou d'une raison similaire, un ou plusieurs serveurs Edge relaient alors le trafic.

4. Le trafic de signalisation est toujours acheminé vers le serveur sur lequel l'utilisateur est domicilié, c'est-à-dire en ligne ou sur site. Un serveur Edge sera utilisé s'il est impossible d'établir une connexion directe au serveur frontal.

5. Les utilisateurs qui rejoignent une conférence hébergée en ligne utiliseront toujours un serveur Edge (ou deux si les configurations de pare-feu du client le nécessitent).

6. Les utilisateurs qui rejoignent une conférence hébergée sur site n'utiliseront généralement pas de serveur Edge s'ils se connectent depuis le même réseau contenant le déploiement sur site, et ils utiliseront un ou deux serveurs Edge lorsqu'ils se connectent depuis l'extérieur de votre réseau.

Pour en savoir plus sur les informations sur le chemin multimédia choisi, voir connectivité de [média à glace](https://aka.ms/AVEdge). Même si cette vidéo est sur Lync Server 2013, les principes et protocoles s’appliquent toujours à Skype entreprise.

## <a name="skype-for-business-call-flows-with-expressroute"></a>Flux d'appels Skype Entreprise avec ExpressRoute

À présent que vous connaissez les quatre segments du réseau et certains principes directeurs généraux pour les flux d’appels Skype entreprise, vous pouvez utiliser ces informations pour vous aider à comprendre le trafic Skype entreprise qui traverse une ExpressRoute segment réseau.

En règle générale, le trafic réseau traverse la connexion ExpressRoute si l'un des points de terminaison se trouve dans votre réseau et si l'autre point de terminaison se trouve dans le centre de données Office 365. Ce trafic comprend le trafic de signalisation entre le client et le serveur, le trafic de médias utilisé lors des téléconférences, ou les appels d'égal à égal qui utilisent un serveur Edge en ligne.

Le trafic ne traverse pas la connexion ExpressRoute si les deux points de terminaison sont en mesure de communiquer directement par le biais d’Internet ou se trouvant au sein de votre réseau. Cela inclut les éléments multimédias pour les appels d’égal à égal, le trafic provenant d’Internet destiné à un déploiement local, ou tout trafic entre les serveurs Microsoft Edge et Internet et 365. Par exemple, un utilisateur rejoint une conférence en ligne à partir d’un hôtel.

## <a name="basic-skype-for-business-call-flow"></a>Flux d'appel de base Skype Entreprise

Afin de vous aider à mettre en application les principes généraux des flux d'appels Skype Entreprise décrits plus haut, la section suivante de cet article comprend plusieurs diagrammes à des fins de référence. Il ne s'agit pas d'une liste exhaustive des différents flux d'appels existants mais d'une aide en vue de la mise en application des principes détaillés plus haut. En outre, les scénarios décrits dans les diagrammes ont été sélectionnés pour couvrir les types de déploiement courants, notamment en ligne, hybrides, Cloud Connector et dans le cas particulier de la diffusion de réunion Skype.

> [!NOTE]
> Un sous-ensemble de trafic utilisé par Skype entreprise n’est pas routable sur ExpressRoute et prend toujours en charge une voie Internet. Reportez-vous aux [URL et plages d’adresses IP Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) pour déterminer les URL qui peuvent être affectées.

### <a name="peer-to-peer-call-for-office-365-users-from-within-customer-network"></a>Appels d’égal à égal pour les utilisateurs d’Office 365 au sein du réseau du client
<a name="bk_Figure2"> </a>

Pour les appels d'égal à égal, le trafic de médias emprunte toujours la route la plus directe pour parvenir à destination. Toutefois, le trafic de signalisation est acheminé jusqu'au centre de données Office 365 dans lequel l'utilisateur en ligne est domicilié. Étant donné que les deux utilisateurs se trouvent sur le même WAN et que rien n'empêche les clients de communiquer directement, les médias sont acheminés directement entre les deux clients. Le trafic de signalisation, pour les deux utilisateurs, traverse la connexion ExpressRoute destinée au centre de données de chaque organisation. Pour afficher le flux d'appels dans ce scénario, reportez-vous au document suivant.

 **Flux d'appels d'égal à égal**

![Call Flow with Peer to Peer call.](../images/f460369e-bfce-4a03-a031-d7e92c4ace89.png)

### <a name="online-user-on-your-network-joining-a-conference-that-is-hosted-online"></a>Utilisateur en ligne sur votre réseau rejoignant une conférence hébergée en ligne
<a name="bk_Figure3"> </a>

Dans l’exemple d’égal à égal, le trafic multimédia effectue toujours l’itinéraire le plus direct vers sa destination. Néanmoins, dans le cas d’une conférence en ligne, la destination se trouve dans le Cloud Office 365. Cela signifie que le trafic multimédia de tous les utilisateurs qui rejoignent la Conférence à partir de votre réseau traverse la connexion ExpressRoute et que le trafic de signalisation navigue vers le Cloud Office 365. Le graphique ci-dessous vous montre que le média et le signalement traversent la connexion ExpressRoute d’un utilisateur au sein de votre réseau, et qu’il traverse directement Internet pour les utilisateurs qui sont connectés à Internet à partir de l’extérieur de votre réseau (par exemple, à partir d’un café). magasin ou hôtel.

N’oubliez pas que l’organisateur d’une conférence est défini par l’organisateur de la réunion et non par les participants. Cela signifie que si la réunion a été planifiée par un client sur site, le trafic de média ne sera pas acheminé vers le Cloud Office 365 sur ExpressRoute, mais serait plutôt acheminé sur Internet vers le centre de donne local de l’organisateur de la réunion.

La destination des médias pour une conférence en ligne sera un centre de données dans le cloud Office 365, le centre de données pouvant toutefois se trouver dans une région géographique différente de celles des utilisateurs qui rejoignent la conférence. Cette situation peut se produire dans deux cas :

- Si l'organisateur de la réunion travaille pour une société différente de celle des participants, et si l'organisation de l'organisateur est hébergée dans une région géographique ou un pays différent

- Si un utilisateur rejoint la réunion depuis une région ou un pays différent de la région ou du pays de l'organisation de la société, soit parce que la société est une multinationale, soit parce que l'utilisateur est en déplacement

Pour plus d’informations sur l’utilisation de ExpressRoute dans le cas présent, c’est qu’avec le module complémentaire ExpressRoute Premium, les données qui suivent le chemin ExpressRoute passe automatiquement du réseau principal de Microsoft, quelle que soit la région géographique de l’organisateur de la réunion. Centre de l’organisation.

 **Flux d'appels d'un utilisateur en ligne pour une réunion en ligne**

![Call flow for an online hosted conference call.](../images/22d9ee64-b20c-4079-b3d1-a7a806b9a0bc.png)

### <a name="joining-a-conference-hosted-by-on-premises-user-in-hybrid-deployment"></a>Rejoindre une conférence hébergée par un utilisateur sur site dans un déploiement hybride
<a name="bk_Figure3"> </a>

Gardez à l’esprit que les serveurs de conférence qui prennent en charge les conférences hébergées sont déterminés par l’emplacement où l’organisateur de la réunion est hébergé. Dans ce scénario, les éléments multimédias pour tous les utilisateurs qui rejoignent une conférence planifiée par un utilisateur sur site dans un déploiement hybride seront acheminés vers un centre de média local. Le signalement pour les utilisateurs familiaux en ligne sera établi par le biais de leur organisation dans le Cloud Office 365, tandis que le contenu multimédia tentera une connexion directe. Dans ce scénario, dans la mesure où les deux utilisateurs se connectent à partir de votre réseau, une connexion directe au média est possible, donc ExpressRoute est utilisé uniquement pour le trafic de signalisation pour l’utilisateur à domicile en ligne. Si un utilisateur à domicile en ligne se connecte à partir d’Internet, le média peut traverser ExpressRoute si un serveur Edge en ligne est utilisé pour la connexion.

 **Flux d'appels d'une conférence hébergée par un utilisateur hybride**

![Call flow hosted onprem.](../images/9e669859-19f3-4a86-95b7-7185eb421ccd.png)

### <a name="on-premises-edge-server-with-office-365-hosted-conferences"></a>Serveur Edge sur site avec conférences hébergées sur Office 365
<a name="bk_Figure5"> </a>

Lorsqu’un utilisateur hybride rejoint une conférence hébergée en ligne, nous savons que le signalement et le contenu multimédia seront destinés au Cloud Office 365, et dans la mesure où l’utilisateur se connecte à partir d’Internet, il est généralement possible de se servir d’un chemin Internet direct. Toutefois, dans certains cas, par exemple en raison de restrictions de pare-feu, un chemin Internet direct n’est pas disponible. Dans ce cas, un serveur Edge sur site peut relayer le trafic multimédia, ce qui amène le trafic multimédia à retourner à votre réseau local avant de traverser le circuit ExpressRoute vers le Cloud Office 365.

 **Utilisateur sur site rejoignant une téléconférence en ligne à l'aide d'un serveur Edge sur site**

![Call flow for a conference call going through an edge server.](../images/0178c170-5837-430d-84f1-582784bfef55.png)

### <a name="pstn-call-using-skype-for-business-cloud-connector-edition"></a>Appel RTC utilisant Skype Entreprise version Cloud Connector
<a name="bk_Figure6"> </a>

L’utilisation de l' [édition Cloud Connector de Skype entreprise Online](https://aka.ms/CloudConnectorInstaller) fournit une connectivité PSTN à l’aide de ressources locales (par exemple, un Trunk SIP ou une passerelle RTC) ou d’un périphérique matériel minimum pour une intégration à Skype entreprise. Avec la version Cloud Connector, les utilisateurs sont hébergés en ligne et agissant en tant qu’utilisateurs normaux en ligne lorsqu’ils n’utilisent pas d’offres d’appels. Le signalement pour les scénarios RTC va voyager entre le client et le Cloud sur une connexion ExpressRoute, s’il est disponible, et le trafic de média reste dans votre réseau WAN. Dans le cas présent, le signalement s’arrête au sein du Cloud Office 365 et se termine par le Cloud Connector.

 **Appel RTC via le système téléphonique dans Office 365 et Cloud Connector**

![Call flow for a PSTN call using Cloud PBX Cloud Connector.](../images/e48d0f2b-fa1e-4b43-b3dd-d34a33dcdf36.png)

### <a name="skype-meeting-broadcast-with-users-joining-from-customer-network"></a>Diffusion de réunion Skype avec des utilisateurs se connectant depuis le réseau du client
<a name="bk_Figure6"> </a>

La fonction diffusion de réunion Skype est un cas d’utilisation spécial, qui consiste en une réunion en deux parties avec des profils de transport réseau différents. La première partie et celle qui est la plus importante du point de vue des performances du réseau sont la réunion interne. Il s’agit de la partie en temps réel de la réunion qui inclut un ou plusieurs points de terminaison client se connectant au serveur de conférence dans le Cloud Office 365. Les données transmises à l’aide de cette partie de la réunion sont exactement les mêmes que l’exemple ci-dessus, avec un utilisateur Office 365 qui rejoint une conférence en ligne.

Ce qui rend la diffusion de réunion Skype unique est que la réunion est distribuée à un grand nombre de participants à la Conférence à l’aide d’un service de diffusion en continu de diffusion. Ce service de diffusion en continu de diffusion n’est pas routable sur ExpressRoute, mais utilise à la place Internet une prise en charge facultative des services de réseau de distribution de contenu (CDN). Il est utile de savoir que le flux de données de diffusion est un flux multimédia unidirectionnel dans la mesure où les participants écoutent sans parler et ne prennent pas en charge la mise en mémoire tampon, ce qui signifie qu’il est beaucoup plus sensible aux problèmes de performances du réseau, tels que la latence, la perte de paquets et le scintillement. Au lieu d’optimiser le trafic de diffusion pour ces problèmes, il est optimisé pour l’utilisation de la bande passante, car un grand nombre de participants peuvent recevoir le contenu multimédia diffusé.

 **Diffusion de réunion Skype avec des utilisateurs depuis le réseau du client**

![Call flow for Skype Meeting Broadcast.](../images/cbe0e9f3-7eee-47e9-b61e-f2780b525dea.png)

## <a name="call-flow-patterns-by-deployment-type"></a>Modèles de flux d'appels par type de déploiement

À l’aide des exemples de flux d’appels courants ci-dessus, et de la connaissance des principes généraux qui contrôlent les modèles de trafic, les tableaux ci-dessous fournissent un résumé des modèles de trafic pour un large éventail de scénarios de déploiement et d’utilisation. Ces tableaux ne capturent pas toutes les combinaisons possibles de flux d’appels, mais doivent vous aider à mieux comprendre les principes généraux du flux d’appels.

Les données sont transmises et sont répertoriées comme étant locales pour l’Organisation ; le réseau du client, Internet ou ExpressRoute ne s’y trouve pas. Les modèles répertoriés ci-dessous sont basés sur les paramètres réseau les plus courants, tels que les pare-feu, la Fédération et l’Internet, et présupposent que toutes les organisations qui participent à des flux multiples ou fédérés ont ExpressRoute. Dans la pratique, il peut s’avérer nécessaire de disposer de différents modèles de trafic que ceux indiqués ci-dessous.

### <a name="call-flows-for-skype-for-business-online"></a>Flux d'appels pour Skype Entreprise Online

Les scénarios d’utilisation de Skype entreprise Online impliquent des utilisateurs hébergés en ligne et peuvent appeler à partir de votre réseau interne ou Internet. Les serveurs sur site ne font pas partie de ces scénarios, de sorte que l’ensemble des conférences ou du contenu multimédia lié à PSTN seront acheminés vers le Cloud Office 365, et le serveur Edge des utilisateurs en ligne sera également dans le Cloud.

 **Flux d'appels résumé pour Skype Entreprise Online**

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Cas d'utilisation** <br/> |**Points de terminaison** <br/> |**Chemin de signalisation** <br/> |**Chemin de médias** <br/> |**Exemple de flux** <br/> |**Remarques** <br/> |
|Appel d'égal à égal  <br/> |Deux clients, tous les deux sur votre réseau.  <br/> |ExpressRoute  <br/> |local  <br/> |[Appels d’égal à égal pour les utilisateurs d’Office 365 au sein du réseau du client](call-flow-using-expressroute.md#bk_Figure2) <br/> ||
|Appel d'égal à égal  <br/> |Deux clients, un sur votre réseau (interne) et l’autre client sur Internet (externe).  <br/> |Utilisateur interne : ExpressRoute  <br/> Utilisateur externe : Internet  <br/> |Utilisateur interne : ExpressRoute  <br/> Utilisateur externe : Internet vers serveur Edge Office 365.  <br/> |[Appels d’égal à égal pour les utilisateurs d’Office 365 au sein du réseau du client](call-flow-using-expressroute.md#bk_Figure2) <br/> |Suppose que le pare-feu bloque les connexions directes entre les clients, qui nécessitent un serveur Edge en ligne. Le trafic d’un utilisateur interne à un serveur Edge en ligne suit le chemin similaire à celui du serveur de conférence pour la conférence téléphonique.  <br/> |
|Appel d'égal à égal vers un utilisateur dans une organisation fédérée  <br/> |Deux clients, un sur votre réseau (interne) et un utilisateur en ligne sur le réseau de l'organisation fédérée (fédéré).  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Utilisateur en ligne sur votre réseau rejoignant une conférence hébergée en ligne](call-flow-using-expressroute.md#bk_Figure3) <br/> |Suppose qu'un pare-feu bloque les connexions directes entre les clients, serveur Edge en ligne requis. Le trafic provenant de l'utilisateur interne à destination du serveur Edge en ligne suit un chemin similaire à celui d'un serveur de conférence pour une téléconférence.  <br/> |
|Rejoindre une téléconférence organisée par un utilisateur sur le réseau du client  <br/> |Client sur votre réseau et serveur de conférence dans le cloud Office 365.  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Utilisateur en ligne sur votre réseau rejoignant une conférence hébergée en ligne](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Rejoindre une téléconférence organisée par un utilisateur sur Internet  <br/> |Le client est sur Internet et le serveur de conférence dans le Cloud Office 365.  <br/> |Internet  <br/> |Internet  <br/> |[Utilisateur en ligne sur votre réseau rejoignant une conférence hébergée en ligne](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Rejoindre une conférence hébergée sur un serveur sur site d'une autre société  <br/> |Client sur votre réseau et serveur de conférence dans un centre de données tiers.  <br/> |Internet  <br/> |Internet  <br/> |Non applicable  <br/> |Étant donné que le serveur de conférence qui héberge la conférence se trouve sur le réseau sur site d'un autre client, aucune donnée ne passe par le cloud Microsoft.  <br/> |
|Appel RTC  <br/> |Client sur le réseau du client et systèmes de téléphone dans le Cloud Office 365  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Utilisateur en ligne sur votre réseau rejoignant une conférence hébergée en ligne](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Appel RTC  <br/> |Client sur Internet et systèmes de téléphone dans le Cloud Office 365  <br/> |Internet  <br/> |Internet  <br/> |Non applicable  <br/> |Le contenu multimédia et le signalement seront acheminés vers le centre de médias Office 365. Dans la mesure où le point de terminaison client est sur Internet, toutes les données sont acheminées vers le centre de données Microsoft sur Internet (même si un serveur Edge en ligne est requis pour la connectivité).  <br/> |

> [!NOTE]
> ExpressRoute sera utilisé sur le chemin multimédia d’un utilisateur situé sur le réseau d’entreprise vers un serveur Edge en ligne, mais il ne sera pas utilisé si le serveur Edge du déploiement local d’un autre client est utilisé.

### <a name="call-flows-for-skype-for-business-hybrid"></a>Flux d'appels hybride pour Skype Entreprise

Les flux d’appels hybrides s’appliquent lorsque vous disposez d’un déploiement Skype entreprise incluant au moins quelques utilisateurs hébergés sur site. Les flux d’appels dans cette section incluent des conférences locales et des appels d’égal à égal ou PSTN avec au moins un utilisateur hébergé sur site.

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Cas d'utilisation** <br/> |**Points de terminaison** <br/> |**Chemin de signalisation** <br/> |**Chemin de médias** <br/> |**Exemple de flux** <br/> |**Remarques** <br/> |
|Appel d'égal à égal  <br/> |Deux clients, tous les deux sur le réseau du client et domiciliés sur site.  <br/> |Local  <br/> |local  <br/> |[Appels d’égal à égal pour les utilisateurs d’Office 365 au sein du réseau du client](call-flow-using-expressroute.md#bk_Figure2) <br/> |Étant donné que les utilisateurs sont domiciliés sur site, le trafic de signalisation est acheminé vers le centre de données sur site et non vers le cloud Office 365.  <br/> |
|Appel d'égal à égal  <br/> |Deux clients, se connectant tous les deux depuis le réseau du client. L'un d'entre eux est domicilié en ligne, l'autre est domicilié sur site.  <br/> |Utilisateur en ligne : ExpressRoute  <br/> Utilisateur sur site : local  <br/> |local  <br/> |[Appels d’égal à égal pour les utilisateurs d’Office 365 au sein du réseau du client](call-flow-using-expressroute.md#bk_Figure2) <br/> |Seul l'utilisateur domicilié en ligne envoie le trafic de signalisation au cloud Office 365.  <br/> |
|Appel d'égal à égal vers un utilisateur dans une organisation fédérée  <br/> |Deux clients, un utilisateur sur site sur le réseau du client (interne) et un utilisateur en ligne sur le réseau de la société fédérée (fédéré).  <br/> |Utilisateur interne : local  <br/> Utilisateur fédéré : ExpressRoute  <br/> |Internet ou ExpressRoute (selon si un serveur Edge en ligne ou sur site est utilisé)  <br/> |[Utilisateur en ligne sur votre réseau rejoignant une conférence hébergée en ligne](call-flow-using-expressroute.md#bk_Figure3) et faisant partie du [serveur Edge sur site avec conférences hébergées sur Office 365](call-flow-using-expressroute.md#bk_Figure5) (pour le trafic de médias). <br/> |Suppose qu’un pare-feu bloque les connexions directes entre les clients et qui nécessitent un serveur Edge en ligne. L’utilisation de la fonction de négociation de glace vous permet d’assurer la connectivité en ligne (par l’utilisateur en ligne) et aux serveurs de périphérie sur site.  <br/> |
|Rejoindre une conférence organisée par un utilisateur sur le réseau du client (conférence organisée par un utilisateur en ligne).  <br/> |Client sur site sur votre réseau et serveur de conférence dans le cloud Office 365.  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Utilisateur en ligne sur votre réseau rejoignant une conférence hébergée en ligne](call-flow-using-expressroute.md#bk_Figure3) <br/> |Les ressources serveur pour la conférence téléphonique sont définies par l’organisateur de la réunion. Dans le cas présent, il a été planifié par un utilisateur en ligne, de sorte que les ressources se trouvent dans le Cloud Office 365.  <br/> |
|Appel RTC  <br/> |Utilisateur sur site sur votre réseau et centre de données Skype Entreprise sur site.  <br/> |Local  <br/> |Local  <br/> |[Appel RTC utilisant Skype Entreprise version Cloud Connector](call-flow-using-expressroute.md#bk_Figure6) <br/> |Scénario similaire à l'utilisation de la version Cloud Connector, sauf que l'utilisateur est domicilié sur site, le trafic de signalisation ne sort donc pas de votre réseau.  <br/> |

### <a name="call-flows-for-skype-for-business-with-cloud-connector"></a>Flux d'appels pour Skype Entreprise avec Cloud Connector

Les utilisateurs qui se connectent à la version Cloud Connector sont tous domiciliés en ligne. Cela signifie que les conférences seront en ligne, et que le trafic de signalisation suivra les mêmes modèles que pour les utilisateurs en ligne. Pour les scénarios autres que les appels RTC, le flux d'appels sera exactement identique au flux décrit ci-dessus pour Skype Entreprise Online.

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Cas d'utilisation** <br/> |**Points de terminaison** <br/> |**Chemin de signalisation** <br/> |**Chemin de médias** <br/> |**Exemple de flux** <br/> |**Remarques** <br/> |
|Appel RTC  <br/> |Utilisateur en ligne sur votre réseau utilisant la version Cloud Connector.  <br/> |local  <br/> |local  <br/> |[Appel RTC utilisant Skype Entreprise version Cloud Connector](call-flow-using-expressroute.md#bk_Figure6) <br/> ||
|Appel RTC  <br/> |Utilisateur en ligne sur Internet utilisant la version Cloud Connector.  <br/> |Internet  <br/> |Internet  <br/> |Combinaison de [serveur Edge sur site avec conférences hébergées sur Office 365 et d'](call-flow-using-expressroute.md#bk_Figure5) [appel RTC utilisant Skype entreprise version Cloud Connector](call-flow-using-expressroute.md#bk_Figure6).  <br/> |Les utilisateurs sur Internet se connecteront via le serveur Edge inclus dans Cloud Connector, et Cloud Connector se connectera au réseau RTC.  <br/> |

## <a name="related-topics"></a>Rubriques connexes

[Documentation ExpressRoute](https://go.microsoft.com/fwlink/?LinkId=690285)


