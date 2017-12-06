---
title: "Flux d'appels avec ExpressRoute"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/9/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: 413acb29-ad83-4393-9402-51d88e7561ab
description: "Cet article décrit les principes du flux d'appels pour Skype Entreprise Online et ExpressRoute, et vous présente des exemples détaillés de flux d'appels afin de vous permettre de comprendre et de planifier correctement."
---

# Flux d'appels avec ExpressRoute

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'[avertissement](413acb29-ad83-4393-9402-51d88e7561ab.md#MT_Footer). Vous pouvez consulter la version en anglais de cet article [ici](https://support.office.com/en-us/article/413acb29-ad83-4393-9402-51d88e7561ab). 
  
Cet article décrit les principes du flux d'appels pour Skype Entreprise Online et ExpressRoute, et vous présente des exemples détaillés de flux d'appels afin de vous permettre de comprendre et de planifier correctement.
  
Si vous déployez Skype entreprise Online dans le cadre d'Office 365, Skype entreprise Server Hybrid ou Skype pour l'édition de connecteur Business Cloud, vous devez comprendre donc la communication entre le Skype pour client Business et les serveurs et le flux d'appels Vous pouvez efficacement planifier, déployer, faire fonctionner et dépanner votre Skype entreprise Online Services.
  
## Présentation du flux d'appels

Ce document décrit le réseau segments qui peuvent comporter des données pour ces appel passe et vous aide à comprendre le trafic qui restera locales à votre réseau par rapport au trafic via Internet ou par le biais ExpressRoute les déplacements. Connaître le trafic qui utilise ExpressRoute vous aidera à évaluer les avantages de votre société recevra à l'aide de ExpressRoute, ainsi que vous aident à que comprendre le Guide de déploiement ExpressRoute pour valider et résoudre les problèmes de votre déploiement une fois que vous avez décidé Pour utiliser ExpressRoute.
  
Les flux d'appels décrits ici peuvent être influencés par différents facteurs dont vous avez la maîtrise, tels que les règles de pare-feu, la configuration NAT, les proxys et la configuration du routeur. Ce document suppose que les paramètres recommandés ont été appliqués. Ces paramètres recommandés sont décrits dans les sections suivantes :
  
- [Configurer Skype Entreprise Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
    
- [URL et plages d'adresses IP Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
    
- [Azure ExpressRoute pour Office 365](https://support.office.com/article/6d2534a2-c19c-4a99-be5e-33a0cee5d3bd)
    
- [Azure ExpressRoute](https://azure.microsoft.com/en-us/services/expressroute/)
    
Le programme d'installation et de configurations qui n'ont pas suivi les étapes de configuration dans la documentation ci-dessus peuvent contenir des flux d'appel autre que celles que nous avons présentés ici. En outre, vous trouverez peut-être vous-même les problèmes de configuration tels qu'itinéraires réseau asymétriques et non optimales ou protocoles de transport non optimal. Routage asymétriques est un facteur important chaque fois que ExpressRoute est impliqué, car ExpressRoute présente un second tracé vers Office 365, il peut arriver pour un itinéraire qui utilise Internet dans une direction et une autre itinéraire qui utilise ExpressRoute dans le sens inverse. Cela peut entraîner le trafic bloqué dans la direction retour si elle parcourt un pare-feu.
  
## Segments réseau et types de trafic

### Segments réseau

Avant de pouvoir décrire les flux d'appels, il est important de définir certains termes afin que vous puissiez comprendre les segments réseau et les types de médias utilisés dans Skype Entreprise Online. 
  
Les diagrammes de flux appel ci-dessous vous montrent quatre différents segments réseau, chacun d'entre eux sont gérés par des organisations différentes (votre réseau interne, votre fournisseur de services de réseau et leurs partenaires Internet et Microsoft) avec différentes caractéristiques de performances. Pour connaître les instructions sur les objectifs de performances réseau, reportez-vous à [Qualité des médias et performances de connectivité réseau dans Skype Entreprise Online](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md).
  
Vous pouvez voir ci-dessous chacun des segments réseau que nous allons aborder.
  
![Call Flow Network Segments.](../images/25689bf2-4753-4bea-b8d7-88dc8b6d2e2a.png)
  
 **Votre réseau** Il s'agit le segment réseau qui fait partie de votre réseau global que vous pouvez contrôler et gérer. Cela inclut toutes les connexions au sein de vos bureaux, si avec ou sans fil, entre bureaux, aux centres de données locale ou pour vos connexions à des fournisseurs Internet ou les partenaires ExpressRoute.
  
En règle générale, le bord de votre réseau a un ou plusieurs DMZ avec pare-feu et/ou des serveurs proxy, qui mettent en œuvre des stratégies de sécurité de votre organisation et qu'Autoriser uniquement certain le trafic réseau que vous avez installé et configuré. Étant donné que vous gérez ce réseau, vous avez contrôle direct sur les performances de votre réseau et il est vivement recommandé que vous effectuez évaluations réseau pour vérifier les performances à la fois dans les sites de votre réseau et à partir de votre réseau pour Skype entreprise En ligne. Pour afficher les exigences de performances, voir [Qualité des médias et performances de connectivité réseau dans Skype Entreprise Online](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md).
  
 **Internet** Il s'agit le segment réseau qui fait partie de votre réseau global qui sera utilisé par les utilisateurs qui vous connectez à Skype entreprise Online à partir d'en dehors de votre réseau et sont utilisés pour toutes les connexions lorsque ExpressRoute n'est pas configuré. Internet et toutes ses connexions ne sont pas gérés par vous ou Microsoft, afin que les performances et les chemins de routage ne peut pas être déterminées et cela créera le plus grand impact sur flux d'appels et la qualité globale.
  
 **ExpressRoute** Il s'agit le segment réseau qui fait partie de votre réseau global qui vous donne une connexion privée dédiée au réseau Microsoft. Il s'agit de l'option recommandée pour connecter votre réseau à Microsoft network (centres de données Office 365) pour toutes les charges de travail qui ne dépendent de la vitesse de réseau et les performances, tels que Skype entreprise Online communication en temps réel. ExpressRoute connexions sont effectuées entre votre réseau et l'utilisation de réseau[fournisseurs de connectivité ExpressRoute](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/) Microsoft à fournir un réseau privé et géré, 99,9 % et prise en charge de la qualité de Service (qualité de service) qui peut améliorer les performances pour les éléments multimédias en temps réel au cours des périodes d'encombrement du réseau.
  
 **Réseau de Microsoft** Il s'agit le segment réseau qui fait partie de votre réseau global qui prend en charge les services Office 365. Cela inclut toutes les communications entre les serveurs Online pour Office 365. Cela peut inclure le trafic qui parcourt le réseau principal Microsoft et transmis entre les régions géographiques.
  
### Types de trafic

Le trafic réseau pour Skype entreprise Online se situe en deux grandes catégories, affichés sous forme de trajectoires distinctes dans le flux d'appels :
  
 **Multimédia en temps réel** est données encapsulées dans RTP (Real-Time Transport Protocol) et prend en charge l'audio, vidéo, partage d'applications et charges de transfert de fichier. En règle générale, le trafic multimédia étant très latence sensible, vous pourriez ce trafic à prendre le chemin le plus direct possible, et pour utiliser UDP comme protocole de la couche transport, car à l'aide de TCP présente latence plus élevée.
  
 **Signalisation** représente le lien de communication entre le client et serveur, ou d'autres clients qui sont utilisés pour contrôler les activités (par exemple, lorsqu'un appel est lancé) et deliver messages instantanés. La plupart des feux de signalisation utilise le protocole SIP, bien que certains clients utilisent les interfaces reste basés sur HTTP. Pour qu'il soit simple, nous allons considérer une variété de signalisation qui peuvent être transmises sur les connexions HTTP et HTTPS ou TLS dans ce type de trafic. Il est important de comprendre que ce trafic est beaucoup moins sensible à la latence, mais peuvent entraîner des interruptions de service ou appel des délais d'expiration si la latence entre les points de terminaison dépasse quelques secondes.
  
Les destinations pour ce trafic sont trouvent dans [URL et plages d'adresses IP Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) pour tous les services Office 365. Pour chaque URL, elle indique si la partie du trafic peut parcourir le ExpressRoute pour Office 365. Pour les diagrammes indiquant qu'Internet est toujours utilisé pour certains types de trafic ExpressRoute est activé, voir[Azure ExpressRoute pour Office 365](https://support.office.com/article/6d2534a2-c19c-4a99-be5e-33a0cee5d3bd). Il est important de comprendre que même URL qui sont répertoriées comme étant pouvant être routés sur ExpressRoute sont également pouvant être routés via Internet. Cela signifie que dans certains cas, la détermination sur si Internet ou ExpressRoute sera utilisé dépend de l'emplacement du client et la configuration des serveurs proxy et de pare-feu. Il est également important de comprendre que dans la mesure où pas toutes les URL associées Office 365 sont en mesure d'utiliser ExpressRoute, une connexion Internet est requise même si vous n'achetez ExpressRoute à partir d'un partenaire ExpressRoute.
  
Le trafic qui ne peut être envoyé via Internet inclut les dépendances Internet courantes, telles que les listes de révocation de certificats (listes de révocation), les recherches DNS et résolution de noms, URL pour les services partagés Office 365, tels que pour le centre d'administration Office 365 et certaines non en temps réel fonctionnalités de communication de Skype entreprise Online, tels que de télémétrie et la fédération pour l'interopérabilité avec grand public de Skype, en tant que multimédias bien est diffusés en continu pour la diffusion de réunion Skype. Pour vous aider à prendre des décisions, voir [Acheminement avec ExpressRoute pour Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408) pour plus d'informations sur lorsque vous planifiez le routage de votre réseau.
  
## Principes du flux d'appels avec Skype Entreprise

Avant d'entrer dans les détails de spécifiques à appeler scénarios de flux, il existe six principes généraux pour vous aider à comprennent les flux d'appel pour Skype entreprise.
  
1. Un Skype pour conférence professionnelle est hébergé dans la même région dans lequel l'organisateur de la conférence est hébergé. Il s'agit dans le cloud Office 365 si l'organisateur est un utilisateur en ligne ou dans un centre de données locale si l'organisateur de la réunion est un utilisateur local.
    
2. Le trafic multimédia envoyé à partir d'un client à une conférence hébergée toujours accède au serveur dans lequel la conférence est hébergée. Cela peut être un serveur local dans un centre de données que vous gérez ou un serveur en ligne au sein du cloud Office 365. Toutefois, un serveur de périphérie est toujours utilisé pour le flux de support pour les conférences en ligne.
    
3. Le trafic de médias pour les appels d'égal à égal emprunte la route la plus directe disponible. La route préférée est la route directe jusqu'à l'homologue distant (client). Si toutefois cette route n'est pas disponible en raison du blocage du trafic par le pare-feu ou d'une raison similaire, un ou plusieurs serveurs Edge relaient alors le trafic.
    
4. Le trafic de signalisation est toujours acheminé vers le serveur sur lequel l'utilisateur est domicilié, c'est-à-dire en ligne ou sur site. Un serveur Edge sera utilisé s'il est impossible d'établir une connexion directe au serveur frontal.
    
5. Les utilisateurs qui rejoignent une conférence hébergée en ligne utiliseront toujours un serveur Edge (ou deux si les configurations de pare-feu du client le nécessitent).
    
6. Les utilisateurs qui rejoignent une conférence hébergée sur site n'utiliseront généralement pas de serveur Edge s'ils se connectent depuis le même réseau contenant le déploiement sur site, et ils utiliseront un ou deux serveurs Edge lorsqu'ils se connectent depuis l'extérieur de votre réseau. 
    
Pour en savoir plus sur les détails sur le chemin d'accès de média est choisie, voir [ICE - connectivité des supports bord](https://aka.ms/AVEdge). Bien que cette vidéo traite de Lync Server 2013, les principes et les protocoles restent appliquent à Skype entreprise.
  
## Flux d'appels Skype Entreprise avec ExpressRoute

Maintenant que vous avez comprendre les quatre différents segments réseau et quelques principes générales pour Skype pour flux appel d'entreprise, vous pouvez utiliser que les informations pour vous aider à comprendre le Skype pour le trafic entreprise seront parcourir un ExpressRoute segment de réseau.
  
En règle générale, le trafic réseau traverse la connexion ExpressRoute si l'un des points de terminaison se trouve dans votre réseau et si l'autre point de terminaison se trouve dans le centre de données Office 365. Ce trafic comprend le trafic de signalisation entre le client et le serveur, le trafic de médias utilisé lors des téléconférences, ou les appels d'égal à égal qui utilisent un serveur Edge en ligne.
  
Le trafic ne parcourt la connexion ExpressRoute si les deux points de terminaison sont en mesure de communiquer directement sur internet ou se trouvent dans votre réseau. Cela doit inclure des éléments multimédias à des appels d'égal à égal, le trafic Internet destiné à un déploiement local ou tout le trafic entre Internet et les serveurs Office 365 Edge. Un exemple de ce serait un utilisateur participation à une conférence en ligne à partir d'un hôtel.
  
## Flux d'appel de base Skype Entreprise

Afin de vous aider à mettre en application les principes généraux des flux d'appels Skype Entreprise décrits plus haut, la section suivante de cet article comprend plusieurs diagrammes à des fins de référence. Il ne s'agit pas d'une liste exhaustive des différents flux d'appels existants mais d'une aide en vue de la mise en application des principes détaillés plus haut. En outre, les scénarios décrits dans les diagrammes ont été sélectionnés pour couvrir les types de déploiement courants, notamment en ligne, hybrides, Cloud Connector et dans le cas particulier de la diffusion de réunion Skype.
  
> [!NOTE]
> Un sous-ensemble de trafic utilisé par Skype entreprise n'est pas pouvant être routé sur ExpressRoute et soit toujours un chemin d'accès Internet. Reportez-vous à [URL et plages d'adresses IP Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) pour déterminer l'URL qui peuvent être affectées.
  
### Appel d'égal à égal pour les utilisateurs d'Office 365 à partir de réseau des clients
<a name="bk_Figure2"> </a>

Pour les appels d'égal à égal, le trafic de médias emprunte toujours la route la plus directe pour parvenir à destination. Toutefois, le trafic de signalisation est acheminé jusqu'au centre de données Office 365 dans lequel l'utilisateur en ligne est domicilié. Étant donné que les deux utilisateurs se trouvent sur le même WAN et que rien n'empêche les clients de communiquer directement, les médias sont acheminés directement entre les deux clients. Le trafic de signalisation, pour les deux utilisateurs, traverse la connexion ExpressRoute destinée au centre de données de chaque organisation. Pour afficher le flux d'appels dans ce scénario, reportez-vous au document suivant.
  
 **Flux d'appels d'égal à égal**
  
![Call Flow with Peer to Peer call.](../images/f460369e-bfce-4a03-a031-d7e92c4ace89.png)
  
### Utilisateur en ligne sur votre réseau rejoignant une conférence hébergée en ligne
<a name="bk_Figure3"> </a>

Dans l'exemple égal à égal, le trafic multimédia prend toujours l'itinéraire plus direct à sa destination. Toutefois, pour une conférence en ligne, la destination est enregistrée dans le cloud Office 365. Cela signifie que le trafic de support pour tous les utilisateurs participation à la conférence à partir de votre réseau parcourt la connexion ExpressRoute et le trafic signalisation se déplace vers le cloud Office 365. L'illustration ci-dessous montre que multimédias et signalisation parcourent la connexion ExpressRoute pour un utilisateur au sein de votre réseau et parcourent directement Internet pour les utilisateurs qui sont connectés à Internet à partir d'à l'extérieur de votre réseau, par exemple à partir d'un café un magasin ou un hôtel.
  
N'oubliez pas que l'emplacement d'une conférence est définie par l'organisateur de la réunion et non par les participants. Cela signifie que si la réunion ont été planifiée par un client local, le trafic multimédia ne déborder dans le cloud Office 365 ExpressRoute, mais plutôt traversent Internet au centre de données locale de l'organisateur de la réunion.
  
La destination des médias pour une conférence en ligne sera un centre de données dans le cloud Office 365, le centre de données pouvant toutefois se trouver dans une région géographique différente de celles des utilisateurs qui rejoignent la conférence. Cette situation peut se produire dans deux cas :
  
- Si l'organisateur de la réunion travaille pour une société différente de celle des participants, et si l'organisation de l'organisateur est hébergée dans une région géographique ou un pays différent
    
- Si un utilisateur rejoint la réunion depuis une région ou un pays différent de la région ou du pays de l'organisation de la société, soit parce que la société est une multinationale, soit parce que l'utilisateur est en déplacement
    
La bonne nouvelle sur l'utilisation de ExpressRoute dans ce scénario est que ExpressRoute premium le module complémentaire, données qui suit le chemin d'accès ExpressRoute passera automatiquement au sein du réseau principal de Microsoft quelle que soit votre région géographique de l'organisateur de la réunion Centre de données de l'organisation.
  
 **Flux d'appels d'un utilisateur en ligne pour une réunion en ligne**
  
![Call flow for an online hosted conference call.](../images/22d9ee64-b20c-4079-b3d1-a7a806b9a0bc.png)
  
### Rejoindre une conférence hébergée par un utilisateur sur site dans un déploiement hybride
<a name="bk_Figure3"> </a>

N'oubliez pas que les serveurs de conférence qui prennent en charge des conférences hébergés sont déterminées par l'endroit où l'organisateur de la réunion est hébergé. Dans ce scénario, support pour tous les utilisateurs participation à une conférence planifiée par un utilisateur local dans un déploiement hybride passera à un centre de données locale. Signalisation des utilisateurs hébergées en ligne est établie au sein de leur organisation dans le Cloud Office 365, tandis que multimédias tentera une connexion directe. Dans ce scénario, étant donné que les deux utilisateurs sont connectent à partir de votre réseau, une connexion media direct est possible afin ExpressRoute est utilisé uniquement pour signalisation le trafic de l'utilisateur hébergée en ligne. Si un utilisateur hébergée en ligne se connecte à partir d'Internet, les éléments multimédias pourraient Parcourir ExpressRoute si un serveur de périphérie en ligne est utilisé pour vous connecter.
  
 **Flux d'appels d'une conférence hébergée par un utilisateur hybride**
  
![Call flow hosted onprem.](../images/9e669859-19f3-4a86-95b7-7185eb421ccd.png)
  
### Serveur Edge sur site avec conférences hébergées sur Office 365
<a name="bk_Figure5"> </a>

Lorsqu'un utilisateur hybride les jointures en ligne hébergé conférence, nous sûr signalisation et éléments multimédias est destiné le cloud Office 365, et dans la mesure où l'utilisateur est rejoindre à partir d'Internet, en règle générale, un chemin d'accès internet direct serait à prendre. Toutefois, dans certains cas, par exemple en raison des restrictions de pare-feu, un chemin d'accès Internet direct n'est pas disponible. Dans ce cas, un serveur de périphérie locaux pouvez relais du trafic multimédia, qui provoque le trafic multimédia revenir à votre réseau local avant de parcourir le circuit ExpressRoute dans le cloud Office 365.
  
 **Utilisateur sur site rejoignant une téléconférence en ligne à l'aide d'un serveur Edge sur site**
  
![Call flow for a conference call going through an edge server.](../images/0178c170-5837-430d-84f1-582784bfef55.png)
  
### Appel RTC utilisant Skype Entreprise version Cloud Connector
<a name="bk_Figure6"> </a>

À l'aide de la [Skype pour l'édition Business Online Cloud connecteur](https://aka.ms/CloudConnectorInstaller) fournit une connectivité PSTN à l'aide des ressources locales comme une jonction SIP ou une passerelle PSTN, ou un périphérique minimales intégrer avec Skype entreprise. Avec l'édition de connecteur Cloud, les utilisateurs sont hébergés en ligne et agissent en tant qu'utilisateurs Online normales quand ils n'impliquent l'appel d'offre. Signalisation pour des scénarios PSTN est véhiculées entre le client et le cloud via une connexion ExpressRoute s'il est disponible, tandis que le trafic multimédia est conforme à votre réseau étendu. Dans ce cas, signalisation désactive dans le cloud Office 365 et se termine au niveau du connecteur Cloud.
  
 **Appel PSTN via le système téléphonique dans Office 365 et lien du Cloud**
  
![Call flow for a PSTN call using Cloud PBX Cloud Connector.](../images/e48d0f2b-fa1e-4b43-b3dd-d34a33dcdf36.png)
  
### Diffusion de réunion Skype avec des utilisateurs se connectant depuis le réseau du client
<a name="bk_Figure6"> </a>

Diffusion de réunion Skype est un spécial cas d'utilisation et composée d'une réunion de deux parties avec chaque partie des profils de transport réseau différente. La première partie et celui qui est le plus important à partir d'un réseau point de vue des performances, est la réunion interne. Il s'agit de la partie en temps réel de la réunion qui inclut un ou plusieurs points de terminaison clients connexion au serveur de conférence dans le cloud Office 365. Données transmises à l'aide de cette partie de la réunion sont exactement comme dans l'exemple ci-dessus, avec une conférence en ligne et de rejoindre des utilisateurs d'Office 365.
  
Diffusion de réunion Skype unique le fait que la réunion est distribuée à un grand nombre de participants à la conférence à l'aide d'une diffusion en continu de service. Cette diffusion en continu de service n'est pas pouvant être routée sur ExpressRoute, mais utilise à la place Internet avec la prise en charge facultatif de services de réseau de remise de contenu (CDN). Il est utile de reconnaissent que la diffusion en continu est un flux multimédia unidirectionnelle étant donné que les participants écoutent, mais ne parlez pas et prend en charge la mise en mémoire tampon, il est beaucoup moins sensible aux problèmes de performances réseau tels que la latence perte de paquets et gigue. Au lieu d'optimiser le trafic de diffusion de ces problèmes, il est optimisé pour l'utilisation de la bande passante, car il existe potentiellement un grand nombre de participants recevoir les éléments multimédias diffusés en continu.
  
 **Diffusion de réunion Skype avec des utilisateurs depuis le réseau du client**
  
![Call flow for Skype Meeting Broadcast.](../images/cbe0e9f3-7eee-47e9-b61e-f2780b525dea.png)
  
## Modèles de flux d'appels par type de déploiement

Avec la commun appelez exemples flux ci-dessus et comprendre les principes généraux qui contrôlent les modèles de trafic, les tableaux suivants fournissent un résumé des modèles de trafic pour une combinaison de grande taille de scénarios de déploiement et l'utilisation. Ces tableaux ne capturez pas toutes les combinaisons possibles de flux d'appel, mais devrait vous aider à mieux comprendre les principes généraux de flux d'appels.
  
Données sont transmises et répertoriées comme étant local à l'organisation ; Il n'a pas laissé le réseau des clients, Internet ou ExpressRoute. Les modèles ci-dessous sont basées sur les paramètres réseau courants, tels que les pare-feu fédération et Internet et part du principe que toutes les organisations impliqués dans plusieurs ou fédérés flux ont ExpressRoute. Dans la pratique, ayant des paramètres différents peut entraîner des modèles de trafic différents de ceux qui sont présentées ci-après.
  
### Flux d'appels pour Skype Entreprise Online

Skype pour entreprise Online scénarios d'utilisation impliquent des utilisateurs qui sont hébergés en ligne et peuvent être appel à partir de votre réseau interne ou sur Internet. Serveurs locale ne font pas partie de ces scénarios, afin que tous les services d'audioconférence ou média associé PSTN passera le cloud Office 365 et les utilisateurs en ligne serveur Edge seront également dans le cloud.
  
 **Flux d'appels résumé pour Skype Entreprise Online**
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Cas d'utilisation** <br/> |**Points de terminaison** <br/> |**Chemin de signalisation** <br/> |**Chemin de médias** <br/> |**Exemple de flux** <br/> |**Remarques** <br/> |
|Appel d'égal à égal  <br/> |Deux clients, tous les deux sur votre réseau.  <br/> |ExpressRoute  <br/> |local  <br/> |[Appel d'égal à égal pour les utilisateurs d'Office 365 à partir de réseau des clients](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure2) <br/> ||
|Appel d'égal à égal  <br/> |Deux clients, sur votre réseau (interne) et l'autre client sur Internet (externe).  <br/> |Utilisateur interne : ExpressRoute  <br/> Utilisateur externe : Internet  <br/> |Utilisateur interne : ExpressRoute  <br/> Utilisateur externe : Internet vers serveur Edge Office 365.  <br/> |[Appel d'égal à égal pour les utilisateurs d'Office 365 à partir de réseau des clients](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure2) <br/> |Suppose que le pare-feu bloque les connexions directe entre les clients, qui nécessite un serveur de périphérie en ligne. Le trafic utilisateur interne vers le serveur de périphérie en ligne suit chemin d'accès similaire que celui au serveur de conférence téléconférence.  <br/> |
|Appel d'égal à égal vers un utilisateur dans une organisation fédérée  <br/> |Deux clients, un sur votre réseau (interne) et un utilisateur en ligne sur le réseau de l'organisation fédérée (fédéré).  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Utilisateur en ligne sur votre réseau rejoignant une conférence hébergée en ligne](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure3) <br/> |Suppose qu'un pare-feu bloque les connexions directes entre les clients, serveur Edge en ligne requis. Le trafic provenant de l'utilisateur interne à destination du serveur Edge en ligne suit un chemin similaire à celui d'un serveur de conférence pour une téléconférence.  <br/> |
|Rejoindre une téléconférence organisée par un utilisateur sur le réseau du client  <br/> |Client sur votre réseau et serveur de conférence dans le cloud Office 365.  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Utilisateur en ligne sur votre réseau rejoignant une conférence hébergée en ligne](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure3) <br/> ||
|Participer à une téléconférence par l'utilisateur dans Internet  <br/> |Client se trouve sur le serveur Internet et les conférences dans Office 365 cloud.  <br/> |Internet  <br/> |Internet  <br/> |[Utilisateur en ligne sur votre réseau rejoignant une conférence hébergée en ligne](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure3) <br/> ||
|Rejoindre une conférence hébergée sur un serveur sur site d'une autre société  <br/> |Client sur votre réseau et serveur de conférence dans un centre de données tiers.  <br/> |Internet  <br/> |Internet  <br/> |Non applicable  <br/> |Étant donné que le serveur de conférence qui héberge la conférence se trouve sur le réseau sur site d'un autre client, aucune donnée ne passe par le cloud Microsoft.  <br/> |
|Appel RTC  <br/> |Client dans le réseau des clients et les serveurs système téléphonique dans Office 365 cloud  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Utilisateur en ligne sur votre réseau rejoignant une conférence hébergée en ligne](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure3) <br/> ||
|Appel RTC  <br/> |Client sur les serveurs Internet et système téléphonique dans Office 365 cloud  <br/> |Internet  <br/> |Internet  <br/> |Non applicable  <br/> |Les éléments multimédias et signalisation will flux au centre de données Office 365. Dans la mesure où le point de terminaison client est connecté à Internet, tous les flux de données au centre de données Microsoft sur Internet (même si un serveur de périphérie en ligne est nécessaire pour la connectivité).  <br/> |
   
> [!NOTE]
> ExpressRoute sera utilisé sur le chemin d'accès de média d'un utilisateur situé sur le réseau d'entreprise à un serveur de périphérie en ligne, mais ne seront pas utilisée si le serveur Edge pour le déploiement local d'un autre client est utilisé. 
  
### Flux d'appels hybride pour Skype Entreprise

Flux d'appel hybride s'appliquent lorsque vous avez un Skype pour le déploiement d'entreprise qui inclut au moins certains utilisateurs qui sont hébergées en local. Les flux d'appel dans cette section incluent les deux conférences en local, égal à égal ou PSTN appelle avec au moins un utilisateur hébergées en local.
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Cas d'utilisation** <br/> |**Points de terminaison** <br/> |**Chemin de signalisation** <br/> |**Chemin de médias** <br/> |**Exemple de flux** <br/> |**Remarques** <br/> |
|Appel d'égal à égal  <br/> |Deux clients, tous les deux sur le réseau du client et domiciliés sur site.  <br/> |Local  <br/> |local  <br/> |[Appel d'égal à égal pour les utilisateurs d'Office 365 à partir de réseau des clients](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure2) <br/> |Étant donné que les utilisateurs sont domiciliés sur site, le trafic de signalisation est acheminé vers le centre de données sur site et non vers le cloud Office 365.  <br/> |
|Appel d'égal à égal  <br/> |Deux clients, se connectant tous les deux depuis le réseau du client. L'un d'entre eux est domicilié en ligne, l'autre est domicilié sur site.  <br/> |Utilisateur en ligne : ExpressRoute  <br/> Utilisateur sur site : local  <br/> |local  <br/> |[Appel d'égal à égal pour les utilisateurs d'Office 365 à partir de réseau des clients](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure2) <br/> |Seul l'utilisateur domicilié en ligne envoie le trafic de signalisation au cloud Office 365.  <br/> |
|Appel d'égal à égal vers un utilisateur dans une organisation fédérée  <br/> |Deux clients, un utilisateur sur site sur le réseau du client (interne) et un utilisateur en ligne sur le réseau de la société fédérée (fédéré).  <br/> |Utilisateur interne : local  <br/> Utilisateur fédéré : ExpressRoute  <br/> |Internet ou ExpressRoute (selon si un serveur Edge en ligne ou sur site est utilisé)  <br/> |[Utilisateur en ligne sur votre réseau rejoignant une conférence hébergée en ligne](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure3) et faisant partie du[Serveur Edge sur site avec conférences hébergées sur Office 365](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure5) (pour le trafic de médias). <br/> |Suppose un pare-feu bloque les connexions directe entre les clients, nécessitant serveur Edge en ligne. GLACE négociation offre en ligne (par l'utilisateur en ligne) et les serveurs de Edge local (par l'utilisateur en local) pour la connectivité.  <br/> |
|Rejoindre une conférence organisée par un utilisateur sur le réseau du client (conférence organisée par un utilisateur en ligne).  <br/> |Client sur site sur votre réseau et serveur de conférence dans le cloud Office 365.  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Utilisateur en ligne sur votre réseau rejoignant une conférence hébergée en ligne](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure3) <br/> |Ressources du serveur de conférence téléphonique sont définies par l'organisateur de la réunion. Dans ce cas, il a été planifié par un utilisateur en ligne, afin que les ressources se trouvent dans le cloud Office 365.  <br/> |
|Appel RTC  <br/> |Utilisateur sur site sur votre réseau et centre de données Skype Entreprise sur site.  <br/> |Local  <br/> |Local  <br/> |[Appel RTC utilisant Skype Entreprise version Cloud Connector](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure6) <br/> |Scénario similaire à l'utilisation de la version Cloud Connector, sauf que l'utilisateur est domicilié sur site, le trafic de signalisation ne sort donc pas de votre réseau.  <br/> |
   
### Flux d'appels pour Skype Entreprise avec Cloud Connector

Les utilisateurs qui se connectent à la version Cloud Connector sont tous domiciliés en ligne. Cela signifie que les conférences seront en ligne, et que le trafic de signalisation suivra les mêmes modèles que pour les utilisateurs en ligne. Pour les scénarios autres que les appels RTC, le flux d'appels sera exactement identique au flux décrit ci-dessus pour Skype Entreprise Online.
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Cas d'utilisation** <br/> |**Points de terminaison** <br/> |**Chemin de signalisation** <br/> |**Chemin de médias** <br/> |**Exemple de flux** <br/> |**Remarques** <br/> |
|Appel RTC  <br/> |Utilisateur en ligne sur votre réseau utilisant la version Cloud Connector.  <br/> |local  <br/> |local  <br/> |[Appel RTC utilisant Skype Entreprise version Cloud Connector](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure6) <br/> ||
|Appel RTC  <br/> |Utilisateur en ligne sur Internet utilisant la version Cloud Connector.  <br/> |Internet  <br/> |Internet  <br/> |Combinaison de [Serveur Edge sur site avec conférences hébergées sur Office 365](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure5) et d'[Appel RTC utilisant Skype Entreprise version Cloud Connector](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure6).  <br/> |Les utilisateurs sur Internet se connecteront via le serveur Edge inclus dans Cloud Connector, et Cloud Connector se connectera au réseau RTC.  <br/> |
   
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Avertissement traduction automatique**: cet article a été traduit par un ordinateur, sans intervention humaine. Microsoft propose cette traduction automatique pour offrir aux personnes ne maîtrisant pas l'anglais l'accès au contenu relatif aux produits, services et technologies Microsoft. Comme cet article a été traduit automatiquement, il risque de contenir des erreurs de grammaire, de syntaxe ou de terminologie.
  

