---
title: Composant Serveur de médiation dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 5b19edef-4a54-43c9-aa12-5643b8108355
description: 'Obtenir des informations sur les serveurs de médiation dans Skype pour Business Server, notamment les topologies prises en charge et ses relations n : n malles, le contournement de média et appel de contrôle d’admission.'
ms.openlocfilehash: a17c6d83c51c8de1101437072f8404202f600e12
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="mediation-server-component-in-skype-for-business-server-2015"></a>Composant Serveur de médiation dans Skype Entreprise Server 2015
 
Obtenir des informations sur les serveurs de médiation dans Skype pour Business Server, notamment les topologies prises en charge et ses relations n : n malles, le contournement de média et appel de contrôle d’admission.
  
Pour déployer les Voix Entreprise, vous devez déployer un ou plusieurs serveurs de médiation. 
  
Le serveur de médiation se traduit par la signalisation entre votre infrastructure de Voix Entreprise interne et d’une passerelle de réseau téléphonique public commuté ou d’un tronc de Session Initiation Protocol (SIP). Dans certains déploiements, il convertit également les éléments multimédias eux-mêmes entre ces points.
  
Sur le côté serveur de l’entreprise Skype, serveur de médiation est à l’écoute sur une adresse de transport mutual TLS (MTLS) unique. Sur le côté de la passerelle, serveur de médiation écoute sur tous les ports d’écoute associés associés à puits qui y aboutissent. Toutes les passerelles qualifiées doivent prendre en charge le protocole TLS mais peuvent aussi activer le protocole TCP. Le protocole TCP est pris en charge pour les passerelles qui ne prennent pas en charge le protocole TLS.
  
Si vous avez également un Public Branch Exchange (PBX existant) dans votre environnement, serveur de médiation gère les appels entre les utilisateurs de Voix Entreprise et PBX. Si votre PBX est un PBX IP, vous pouvez créer une connexion SIP directe entre le PBX et un serveur de médiation. Si votre PBX est un moment de Division Multiplex (TDM) PBX, vous devez également déployer une passerelle PSTN entre PBX et le serveur de médiation.
  
Par défaut, le serveur de médiation est colocalisé avec le serveur frontal. Le serveur de médiation peut également être déployé dans un pool autonome.
  
## <a name="what-mediation-server-does"></a>Rôle du serveur de médiation

Les principales fonctions du serveur de médiation sont les suivantes :
  
- Cryptage et décryptage des SRTP sur le Skype pour le côté serveur de l’entreprise. 
    
- Conversion SIP sur TCP (pour les passerelles non compatibles TLS) vers SIP sur MTLS (Mutual TLS).
    
- Conversion de flux de données entre Skype pour Business Server et de l’homologue de la passerelle du serveur de médiation.
    
- Connexion des clients situés hors du réseau aux composants ICE internes, ce qui permet aux données multimédias de traverser les convertisseurs d’adresses réseau (NAT) et les pare-feu.
    
- Faisant office d’intermédiaire pour les flux d’appel de passerelle ne pouvant pas, par exemple les appels des travailleurs à distance sur un clien.t de Voix Entreprise
    
- Dans les déploiements qui incluent la jonction SIP, collaboration avec le fournisseur de services de jonction SIP pour fournir la prise en charge RTC, de sorte qu’il ne soit plus nécessaire de disposer d’une passerelle RTC.
    
La figure suivante montre les protocoles de signalisation et de media qui sont utilisés par le serveur de médiation pour communiquer avec une passerelle PSTN de base et de l’infrastructure de Voix Entreprise.
  
**Protocoles de signalisation et les média utilisés par le serveur de médiation**

![Diagramme de protocoles de serveur de médiation](../../media/c3d39ba0-e323-4a58-8f07-4e80d3278af2.jpg)
  
> [!NOTE]
> Si vous utilisez TCP ou RTP/RTCP (au lieu de SRTP ou SRTCP) sur le réseau entre la passerelle RTC et le serveur de médiation, nous vous recommandons de vous prenez des mesures pour garantir la sécurité et la confidentialité du réseau. 
  
## <a name="mn-trunk"></a>Jonction M:N

Skype pour Business Server prend en charge la flexibilité dans la définition d’un tronc à des fins de routage appel. Une ligne est une association logique entre un serveur de médiation et d’un numéro de port d’écoute, avec une passerelle et un numéro de port d’écoute. Cela implique plusieurs choses : un serveur de médiation peut avoir plusieurs puits pour la même passerelle ; un serveur de médiation peut avoir plusieurs puits y différentes passerelles ; à l’inverse, une passerelle peut avoir plusieurs troncs à différents serveurs de médiation.
  
Vous devez toujours créer un tronc racine lorsque vous ajoutez une passerelle vers votre Skype pour la topologie d’entreprise à l’aide du Générateur de topologies. Le nombre de passerelles capable de gérer un serveur de médiation donné dépend de la capacité de traitement du serveur pendant les heures de disponibilité de pointe. Si vous déployez un serveur de médiation sur du matériel qui répond à la configuration minimale requise pour Skype pour Business Server, comme décrit dans [configuration du serveur pour Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md), un serveur de médiation autonome peut gérer environ appels de 1000. Le serveur de médiation est effectue le transcodage, mais continuer à acheminer les appels pour plusieurs passerelles même si les passerelles ne prennent pas en charge le contournement de média.
  
Lorsque vous définissez un itinéraire d’appel, vous spécifiez les trunks associés à cet itinéraire, mais que vous ne spécifiez pas les serveurs de médiation associés à cet itinéraire. Au lieu de cela, vous utilisez Générateur de topologies pour associer des puits avec les serveurs de médiation. En d’autres termes, le routage détermine le tronc à utiliser pour un appel et, par la suite, le serveur de médiation associé à cette jonction est envoyé à la signalisation pour cet appel.
  
Le serveur de médiation peut être déployé comme un pool ; ce pool peut être colocalisé avec un pool frontal, ou il peut être déployé comme un pool de ressources autonomes. Lorsqu’un serveur de médiation est colocalisé avec un pool frontal, la taille du pool peut être au plus 12 (limite de la taille du pool de Registrar). Ensemble, ces capacités augmentent la fiabilité et la flexibilité de déploiement pour les serveurs de médiation, mais ils requièrent des fonctionnalités similaires dans le code suivant :
  
- **Passerelle RTC.** Un Skype pour passerelle qualifié de serveur d’entreprise doit implémenter l’équilibrage de charge DNS, qui permet à une passerelle de réseau (RTPC) qualifié téléphonique commuté agir comme un équilibreur de charge d’un pool de serveurs de médiation et, par conséquent, les appels de l’équilibrage de charge sur le pool .
    
- **Contrôleur de bordure de session.** Pour un SIP trunk, l’entité de l’homologue est un contrôleur de bordure de Session (SBC) à un fournisseur de services de téléphonie. Dans le sens à partir du pool de serveur de médiation de la colonie d’abeilles simulée, le SBC peut recevoir des connexions à partir de n’importe quel serveur de médiation dans le pool. Dans la direction de la colonie d’abeilles simulée pour le pool, le trafic peut être envoyé à un serveur de médiation dans le pool. Une méthode de parvenir est via DNS équilibrage de charge, si pris en charge par le fournisseur de services et de la colonie d’abeilles simulée. Une alternative consiste à donner au fournisseur de services les adresses IP de tous les serveurs de médiation dans le pool, et le fournisseur de services met en service dans leur colonie d’abeilles simulée comme un SIP trunk distinct pour chaque serveur de médiation. Le fournisseur de services gère ensuite l’équilibrage de charge pour ses propres serveurs. Pas de tous les fournisseurs de services ou SBCs peuvent prendre en charge ces fonctionnalités. En outre, le fournisseur de services peut facturer un supplément pour cette fonctionnalité. En général, chaque SIP trunk à le SBC entraîne un abonnement mensuel.
    
- **IP-PBX.** Dans la direction à partir du pool de serveur de médiation à la fin de l’IP-PBX SIP, l’IP-PBX peut recevoir des connexions à partir de n’importe quel serveur de médiation dans le pool. Dans la direction de l’IP-PBX pour le pool, le trafic peut être envoyé à un serveur de médiation dans le pool. IP-PBX de la plupart des ne prennent pas en charge l’équilibrage de la charge DNS, nous vous recommandons que chaque connexion SIP directe défini à partir de l’IP-PBX pour chaque serveur de médiation dans le pool. L’IP-PBX gère ensuite son propre équilibrage en répartissant le trafic sur le groupe agrégé. L’hypothèse est que le groupe agrégé a un ensemble cohérent de règles de routage à l’IP-PBX. Si tel IP-PBX prend en charge ce concept de groupe trunk et comment il croise la redondance de le de IP-PBX propre et architecture de clustering doit être déterminée avant de déterminer si un cluster de serveur de médiation peut interagir correctement avec un PBX IP.
    
Un pool de serveur de médiation doit disposer d’une vue uniforme de la passerelle homologue avec lequel elle interagit. Cela signifie que tous les membres du pool accèdent à la même définition de passerelle homologue à partir du magasin de configurations et qu’ils ont tous autant de chances d’interagir avec elle pour les appels sortants. Par conséquent, il n’existe aucun moyen de segmenter le pool afin que certains serveurs de médiation communiquer avec uniquement certains homologues de passerelle pour les appels sortants. Si cette segmentation est nécessaire, un pool distinct des serveurs de médiation doit être utilisé. Ce serait le cas, par exemple, si les fonctionnalités associées dans les passerelles RTC, jonctions SIP ou systèmes IP-PBX pour interagir avec un pool n’étaient pas présentes (voir plus haut dans cette rubrique).
  
Une passerelle RTPC, IP-PBX ou homologue de jonction SIP peut router vers plusieurs serveurs de médiation ou les puits qui y aboutissent. Le nombre de passerelles qui contrôle l’un pool spécifique de serveurs de médiation dépend du nombre d’appels qui utilisent le contournement de média. Si un grand nombre d’appels utiliser le contournement de média, un serveur de médiation dans le pool peut gérer plus grand nombre d’appels, étant donné que le seul traitement de couche de signalisation est nécessaire. 
  
## <a name="call-admission-control-and-mediation-server"></a>Contrôle d’admission des appels et serveur de médiation

Le contrôle d’admission des appels (CAC) gère l’établissement de session en temps réel en tenant compte de la bande passante disponible pour éviter toute dégradation de la qualité de l’expérience (QoE) pour les utilisateurs sur des réseaux saturés. Pour ce faire, le serveur de médiation est responsable de la gestion de bande passante pour ses deux interactions sur le Skype pour le côté serveur de l’entreprise et sur le côté de la passerelle. Dans le cadre du contrôle d’admission des appels, l’entité qui met fin à l’appel gère la réservation de la bande passante. Les homologues de gateway (passerelle PSTN, IP-PBX, SBC) interagissant avec le serveur de médiation sur le côté de la passerelle ne permettent pas de Skype Business Server appel de contrôle d’admission. Par conséquent, le serveur de médiation doit gérer des interactions de la bande passante pour le compte de son homologue de passerelle. Chaque fois que possible, le serveur de médiation réserver à l’avance la bande passante. Si c’est impossible (par exemple, si la localité du point de terminaison multimédia final du côté passerelle est inconnue pour un appel sortant vers l’homologue de passerelle), la bande passante est réservée quand l’appel est passé. Ce comportement peut entraîner une sur-souscription de bande passante, mais c’est le seul moyen d’empêcher les sonneries factices.
  
La déviation du trafic multimédia et la réservation de bande passante s’excluent mutuellement. Si la déviation du trafic multimédia est utilisée pour un appel, le contrôle d’admission des appels n’est pas effectué pour cet appel. L’hypothèse repose sur le fait qu’aucun lien avec bande passante restreinte n’est impliqué dans l’appel. Si l’appel de contrôle d’admission est utilisé pour un appel particulier qui implique le serveur de médiation, cet appel ne peut pas utiliser le contournement de média.
  
Pour plus d’informations sur les médias ignorer ou appeler le contrôle d’admission, voir le [Plan de support ignorer dans Skype pour entreprise 2015](media-bypass.md) ou le [Plan d’appel de contrôle d’admission dans Skype pour Business Server 2015](call-admission-control.md).
  
## <a name="enhanced-9-1-1-e9-1-1-and-mediation-server"></a>Enhanced 9-1-1 (E9-1-1) et serveur de médiation

Le serveur de médiation possède des capacités étendues afin qu’il peut interagir correctement avec les fournisseurs de service Enhanced 9-1-1 (E9-1-1). Aucune configuration particulière n’est nécessaire sur le serveur de médiation. Les extensions SIP requises pour l’interaction E9-1-1 sont, par défaut, incluse dans le protocole SIP du serveur de médiation pour ses interactions avec un homologue gateway (passerelle PSTN, IP-PBX ou la colonie d’abeilles simulée d’un fournisseur de Service de téléphonie Internet, y compris Service E9-1-1 Fournisseurs)
  
Si le SIP trunk à un fournisseur de Service E9-1-1 peut être terminée dans un pool de serveur de médiation existant nécessite des serveurs de médiation autonome dépend de si la SBC E9-1-1 peut interagir avec un pool de serveurs de médiation. Pour plus d’informations, reportez-vous à la section [trunk n : n dans Skype pour Business Server 2015](m-n-trunk.md).
  
## <a name="media-bypass-and-mediation-server"></a>Déviation du trafic multimédia et serveur de médiation

Le contournement de média est un Skype pour la fonction de serveur d’entreprise qui permet à un administrateur de configurer le routage des appels pour placer directement entre l’extrémité de l’utilisateur et de la passerelle de réseau téléphonique public commuté, sans parcourir le serveur de médiation. Le contournement de média en réduisant le temps de latence, la traduction inutile, possibilité de perte de paquets et le nombre de points de défaillance potentiels, ce qui améliore la qualité de l’appel. Dans le cas où un site distant sans serveur de médiation est connecté à un site central par un ou plusieurs liens WAN avec une bande passante limitée, le contournement de média réduit le besoin en bande passante en activant le média à partir d’un client sur un site distant à circuler directement vers sa passerelle locale sans tout d’abord avoir à circuler à travers le WAN créer un lien vers un serveur de médiation sur le site central et la sauvegarder. Cette réduction dans le traitement des médias également complète la capacité du serveur de médiation pour contrôler plusieurs passerelles.
  
La déviation du trafic multimédia et le contrôle d’admission des appels s’excluent mutuellement. Si la déviation du trafic multimédia est utilisée pour un appel, le contrôle d’admission des appels n’est pas effectué pour cet appel. L’hypothèse repose sur le fait qu’aucun lien avec bande passante restreinte n’est impliqué dans l’appel.
  
## <a name="topologies-for-mediation-server"></a>Topologies du serveur de médiation

Le Skype pour Business Server, serveur de médiation est par défaut colocalisé avec le serveur Standard Edition, un pool frontal ou Survivable Branch Appliance. Tous les serveurs de médiation dans un pool frontal doit être configurés de la même manière.
  
Dans le cas où les performances sont un problème, il peut être préférable de déployer un ou plusieurs serveurs de médiation dans un pool autonome dédié. Nous vous conseillons absolument un pool autonome si vous déployez une jonction SIP. 
  
Si vous déployez des connexions de SIP Direct à une passerelle PSTN qualifiée qui prend en charge le contournement de média et DNS charge équilibrage de charge, un serveur de médiation autonome pool n’est pas nécessaire. C’est parce que les passerelles qualifiés sont en mesure de DNS d’équilibrage de charge à un pool de serveurs de médiation et qu’ils peuvent recevoir du trafic à partir de n’importe quel serveur de médiation dans un pool.
  
Nous vous recommandons également de colocaliser sur un pool frontal, le serveur de médiation lorsque vous avez déployé l’IP-PBX ou se connectez à un Internet serveur fournisseur de téléphonie Session contrôleur périphérie (SBC), tant qu’une des conditions suivantes sont remplie :
  
- L’IP-PBX ou SBC est configuré pour recevoir le trafic provenant de n’importe quel serveur de médiation dans le pool et peut router le trafic uniformément à tous les serveurs de médiation dans le pool.
    
- L’IP-PBX ne gère pas le contournement de média, mais le pool frontal qui héberge le serveur de médiation peut gérer le transcodage de voix pour les appels qui ne s’applique pas le contournement de média.
    
Vous pouvez utiliser Microsoft Lync Server 2013, outil de planification pour évaluer si le pool frontal où vous souhaitez colocaliser le serveur de médiation peut gérer la charge. Si votre environnement ne répond pas à ces exigences, vous devez déployer un pool de serveur de médiation autonome.
  
La figure suivante montre une topologie simple constituée de deux sites connectés par une liaison de réseau étendu. Serveur de médiation se trouve sur un pool frontal au Site 1. Les serveurs de médiation au Site 1 contrôle la passerelle RTC au Site 1 et la passerelle au Site 2. Dans cette topologie, la déviation du trafic multimédia est activée globalement afin d’utiliser les informations de site et de région, et le contournement est activé sur les jonctions vers chaque passerelle RTC (GW1 et GW2).
  
**Exemple de sites connectés par un réseau étendu lien avec un serveur de médiation au Site 1 et une passerelle PSTN au Site 2**

![Topologie vocale avec passerelle WAN de serveur de médiation](../../media/Plan_LyncServer_Voice_Topo_MedSvrWanGwy.jpg)
  
La figure suivante illustre une topologie simple dans lequel le serveur de médiation se trouve sur le pool frontal au Site 1 et dispose d’une connexion SIP Direct à IP-PBX sur Site 1. Dans cette figure, le serveur de médiation contrôle également une passerelle PSTN au Site 2. Supposons que Skype pour les entreprises situées dans les Sites 1 et 2. Supposons également que l’IP-PBX doté d’un processeur de média associé qui doit être parcouru par tous les supports provenant de Skype pour les points de terminaison entreprise avant d’être envoyées aux points de terminaison de médias contrôlés par le PBX IP. Dans cette topologie, la déviation du trafic multimédia est activée globalement pour utiliser les informations de site et de région, et il est activé pour les jonctions vers la passerelle PBX et RTC.
  
**Exemple de sites connectés par un réseau étendu lien avec un serveur de médiation au Site 1 et d’un système PBX sur Site 2**

![Topologie vocale - PBX WAN de serveur de médiation](../../media/Plan_LyncServer_Voice_Topo_MedSvrWanPbx.jpg)
  
La dernière figure dans cette rubrique illustre une topologie où le serveur de médiation est connecté à la colonie d’abeilles simulée d’un fournisseur de services de téléphonie. 
  
## <a name="planning-decisions-for-mediation-server"></a>Décisions de planification relatives au serveur de médiation

Cette rubrique décrit les décisions que vous devez créer pour votre déploiement de serveur de médiation,
  
### <a name="collocated-or-stand-alone-mediation-server"></a>Serveur de médiation colocalisé ou autonome ?

Par défaut serveur de médiation se trouve sur le serveur Standard Edition server ou un serveur frontal dans un pool frontal sur les sites centraux. Le nombre d’appels RTC (réseau téléphonique commuté) pouvant être gérés et le nombre d’ordinateurs requis dans le pool dépendront des éléments suivants :
  
- Le nombre de pairs de passerelle contrôlant le pool de serveur de médiation
    
- des périodes de trafic aux heures de pointe via ces passerelles ;
    
- Le pourcentage d’appels appels dont media ignore le serveur de médiation
    
Lors de la planification, veillez à prendre en compte le support de traitement requises pour les appels RTPC et A / vidéoconférences qui ne sont pas configurés pour support de dérivation, ainsi que le traitement nécessaire pour gérer des interactions de signalisation pour le nombre d’appels d’heure devant prise en charge. S’il n’a pas suffisamment de processeur, vous devez déployer un pool autonome, des serveurs de médiation ; et les passerelles RTPC, IP-PBX et SBCs devra diviser en sous-ensembles qui sont contrôlées par les serveurs de médiation colocalisée dans un pool et les serveurs de médiation autonome dans un ou plusieurs pools autonomes.
  
Si vous avez déployé des passerelles RTPC, IP-PBX ou contrôleurs de bordure de Session (SBCs) qui ne prennent pas en charge les fonctionnalités correctes pour interagir avec un pool de serveurs de médiation, y compris les éléments suivants, puis ils devront être associé à un pool autonome comprenant d’un seul serveur de médiation :
  
- Effectuer la couche réseau nom de domaine (DNS) répartition des charges sur les serveurs de médiation dans un pool (ou sinon router le trafic uniformément à tous les serveurs de médiation dans un pool)
    
- Accepter le trafic à partir de n’importe quel serveur de médiation dans un pool
    
Vous pouvez utiliser le Microsoft Lync Server 2013, outil de planification pour évaluer si COLLOCATION avec votre pool frontal, le serveur de médiation peut gérer la charge. Si votre environnement ne répond pas à ces exigences, vous devez déployer un pool de serveur de médiation autonome.
  
### <a name="central-site-and-branch-site-considerations"></a>Considérations relatives au site central et aux sites de succursale

 Des serveurs de médiation sur le site central peuvent être utilisés pour acheminer les appels pour IP-PBX ou passerelles RTPC sur les sites des succursales. Toutefois, si vous déployez les trunks SIP, vous devez déployer un serveur de médiation sur le site où chaque ligne se termine. Avoir un serveur de médiation au niveau du site central acheminer les appels pour une passerelle PSTN ou un IP-PBX à un site de la succursale ne nécessite pas l’utilisation de médias ignorer. Cependant, si vous pouvez l’activer, vous pourrez réduire la latence du chemin d’accès des médias et améliorer la qualité des médias car le chemin d’accès des médias n’est plus nécessaire pour suivre le chemin de signalisation. Le contournement de média réduit également la charge de traitement sur le pool.
  
> [!NOTE]
> La déviation du trafic multimédia ne va pas interagir avec chaque passerelle RTC, chaque système IP-PBX et chaque contrôleur SBC. Microsoft a testé un ensemble de passerelles RTC et des contrôleurs SBC avec des partenaires certifiés et a effectué des tests avec des systèmes IP-PBX de Cisco. Le contournement de média est pris en charge uniquement avec les produits et versions répertoriées au [Unified Communications Ouvrir programme d’interopérabilité - Lync Server](https://go.microsoft.com/fwlink/p/?LinkId=268730). 
  
Si la résilience de site de succursale est requise, un Survivable Branch Appliance ou une combinaison d’un serveur frontal et un serveur de médiation, une passerelle doit être déployé sur le site de la succursale. (La prise en charge avec la résilience de site de succursale est que présence et les conférences ne sont pas résilientes sur le site.) Pour obtenir des instructions sur le site de la succursale de planification pour la voix, consultez [planification de résilience de Voix Entreprise dans Skype pour Business Server 2015](enterprise-voice-resiliency.md).
  
Pour les interactions avec un PBX IP, si l’IP-PBX ne gère pas correctement anticipée interactions media avec plusieurs boîtes de dialogue précoces et des interactions de la RFC 3960, il peut y avoir d’écrêtage des premiers mots de la carte de vœux pour les appels entrants à partir de l’IP-PBX à Skype pour Points de terminaison Business. Ce problème peut être plus grave si un serveur de médiation dans un site central est acheminement d’appels pour un IP-PBX où l’itinéraire met fin à un site de la succursale, car plus de temps est nécessaire pour la signalisation terminer. Si vous rencontrez ce problème, déployez un serveur de médiation au site de la succursale est la seule façon de réduire l’écrêtage du premier peu de mots.
  
Enfin, si votre site central a un PBX TDM, ou si votre PBX IP n’élimine pas la nécessité d’une passerelle RTPC, vous devez déployer une passerelle sur l’itinéraire de l’appel de connexion de serveur de médiation et le PBX.
  
> [!NOTE]
> Pour améliorer les performances multimédias d’un serveur de médiation autonome, activez RSS (Receive-Side Scaling) sur les cartes réseau de ces serveurs. RSS permet la gestion en parallèle des paquets entrants par plusieurs processeurs sur le serveur. Pour plus d’informations, consultez [« côté réception mise à l’échelle améliorations dans Windows Server ».](https://go.microsoft.com/fwlink/p/?LinkId=268731) Pour plus d’informations sur l’activation de RSS, reportez-vous à la documentation de votre carte réseau. 
  

