---
title: Composant serveur de médiation dans Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5b19edef-4a54-43c9-aa12-5643b8108355
description: 'Découvrez les serveurs de médiation Skype pour Business Server, y compris ses topologies prises en charge et ses relations à jonctions m : n, le contournement de média et contrôle d’admission des appels.'
ms.openlocfilehash: ef6076fed4c254180837d6bcdd3e4954f9f94dec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33913745"
---
# <a name="mediation-server-component-in-skype-for-business-server"></a>Composant serveur de médiation dans Skype pour Business Server
 
Découvrez les serveurs de médiation Skype pour Business Server, y compris ses topologies prises en charge et ses relations à jonctions m : n, le contournement de média et contrôle d’admission des appels.
  
Pour déployer Enterprise Voice, vous devez déployer un ou plusieurs serveurs de médiation. 
  
Le serveur de médiation traduit la signalisation entre votre infrastructure Enterprise Voice interne et une passerelle de réseau téléphonique commuté ou une jonction de protocole SIP (Session Initiation). Dans certains déploiements, il convertit également les éléments multimédias eux-mêmes entre ces points.
  
Sur Skype pour côté Business Server, serveur de médiation écoute une seule adresse de transport mutual TLS (MTLS). Sur le côté de la passerelle, le serveur de médiation écoute sur tous les ports d’écoute associés associés jonctions. Toutes les passerelles qualifiées doivent prendre en charge le protocole TLS mais peuvent aussi activer le protocole TCP. Le protocole TCP est pris en charge pour les passerelles qui ne prennent pas en charge le protocole TLS.
  
Si vous avez également un Public Branch Exchange (PBX existant) dans votre environnement, le serveur de médiation gère les appels entre les utilisateurs d’Enterprise Voice et le système PBX. Si votre système PBX est un IP-PBX, vous pouvez créer une connexion SIP directe entre le système PBX et le serveur de médiation. Si votre système PBX est un temps Division multiplexage (TDM) PBX, vous devez également déployer une passerelle PSTN entre le serveur de médiation et le système PBX.
  
Par défaut, le serveur de médiation est colocalisé avec le serveur frontal. Le serveur de médiation peut être déployé dans un pool autonome.
  
## <a name="what-mediation-server-does"></a>Rôle du serveur de médiation

Les principales fonctions du serveur de médiation sont comme suit :
  
- Chiffrement et déchiffrement SRTP sur le Skype côté serveur de l’entreprise. 
    
- Conversion SIP sur TCP (pour les passerelles non compatibles TLS) vers SIP sur MTLS (Mutual TLS).
    
- Traduction des flux de données multimédias entre Skype pour Business Server et l’homologue de passerelle du serveur de médiation.
    
- Connexion des clients situés hors du réseau aux composants ICE internes, ce qui permet aux données multimédias de traverser les convertisseurs d’adresses réseau (NAT) et les pare-feu.
    
- Rôle d’intermédiaire pour les flux d’appels une passerelle ne prenant pas en charge, tels que les appels de travailleurs distants sur un clien.t Enterprise Voice
    
- Dans les déploiements qui incluent la jonction SIP, collaboration avec le fournisseur de services de jonction SIP pour fournir la prise en charge RTC, de sorte qu’il ne soit plus nécessaire de disposer d’une passerelle RTC.
    
La figure suivante illustre les protocoles de signalisation et des médias utilisés par le serveur de médiation lors de la communication avec une passerelle PSTN de base et l’infrastructure Enterprise Voice.
  
**Protocoles de signalisation et de données multimédias utilisés par le serveur de médiation**

![Diagramme de protocoles de serveur de médiation](../../media/c3d39ba0-e323-4a58-8f07-4e80d3278af2.jpg)
  
> [!NOTE]
> Si vous utilisez TCP ou RTP/RTCP (au lieu de SRTP ou SRTCP) sur le réseau entre la passerelle PSTN et le serveur de médiation, nous vous recommandons de prendre des mesures afin de garantir la sécurité et confidentialité du réseau. 
  
## <a name="mn-trunk"></a>Jonction M:N

Skype pour Business Server prend en charge la flexibilité dans la définition d’une jonction à des fins de routage appel. Un tronçon est une association entre un serveur de médiation et le numéro de port d’écoute, logique avec une passerelle et un numéro de port d’écoute. Cela implique plusieurs tâches : un serveur de médiation peut avoir plusieurs jonctions vers la même passerelle ; un serveur de médiation peut avoir plusieurs jonctions à différentes passerelles ; Inversement, une passerelle peut avoir plusieurs jonctions à différents serveurs de médiation.
  
Vous devez toujours créer une jonction racine lorsque vous ajoutez une passerelle vers votre Skype pour la topologie d’entreprise à l’aide du Générateur de topologie. Le nombre de passerelles capable de gérer un serveur de médiation donné dépend de la capacité de traitement du serveur pendant les heures de pointe occupé (e). Si vous déployez un serveur de médiation sur du matériel conforme à la configuration matérielle minimale requise pour Skype pour Business Server, comme décrit dans la [configuration serveur requise pour Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md), un serveur de médiation autonome peut gérer environ appels 1000. Le serveur de médiation est effectue transcodage, mais toujours acheminer les appels de plusieurs passerelles, même si les passerelles ne prennent pas en charge le contournement de média.
  
Lorsque vous définissez un itinéraire d’appel, vous spécifiez les jonctions associées à cet itinéraire, mais vous ne spécifiez pas qui sont des serveurs de médiation associés à cet itinéraire. Au lieu de cela, vous utilisez le Générateur de topologie pour associer des jonctions avec les serveurs de médiation. En d’autres termes, routage détermine quels jonction à utiliser pour un appel et, par la suite, le serveur de médiation associé à ce tronçon est envoyé à la signalisation d’appel.
  
Le serveur de médiation peut être déployé en tant que pool ; ce pool peut être colocalisé avec un pool frontal, ou elle peut être déployé comme un pool autonome. Lorsqu’un serveur de médiation est colocalisé avec un pool frontal, la taille du pool peut être au plus 12 (la limite de la taille du pool de serveurs d’inscriptions). Ensemble, ces fonctionnalités augmentent la fiabilité et la flexibilité de déploiement de serveurs de médiation, mais ils nécessitent des fonctionnalités similaires dans les éléments suivants :
  
- **Passerelle RTC.** Un Skype pour la passerelle Business Server complet doit implémenter l’équilibrage de charge DNS, ce qui permet une passerelle de réseau (PSTN) public commuté complet agir comme un équilibreur de charge pour un pool de serveurs de médiation et donc d’équilibrer les appels entre le pool .
    
- **Contrôleur de session en périphérie.** Pour une jonction SIP, l’entité homologue est un contrôleur de frontière de Session (SBC) à un fournisseur de services de téléphonie Internet. Dans le sens du pool de serveurs de médiation pour le contrôleur SBC, le contrôleur SBC peut recevoir des connexions à partir de n’importe quel serveur de médiation du pool. Dans le sens le contrôleur SBC vers le pool, le trafic peut être envoyé vers n’importe quel serveur de médiation du pool. Une méthode de parvenir consiste via l’équilibrage de charge DNS pris en charge par le fournisseur de services et SBC. Une alternative consiste à donner le fournisseur de services les adresses IP de tous les serveurs de médiation du pool et le fournisseur de services met en service dans leur SBC comme une jonction SIP distincte pour chaque serveur de médiation. Le fournisseur de services gère ensuite l’équilibrage de charge pour ses serveurs. Pas de tous les fournisseurs de services ou SBCs peuvent prendre en charge ces fonctionnalités. En outre, le fournisseur de services peut frais supplémentaires pour cette fonctionnalité. En règle générale, chaque jonction SIP pour le contrôleur SBC entraîne un abonnement mensuel.
    
- **IP-PBX.** Dans le sens du pool de serveurs de médiation à la fin de l’IP-PBX SIP, le système IP-PBX peut recevoir des connexions à partir de n’importe quel serveur de médiation du pool. Dans le sens de l’IP-PBX vers le pool, le trafic peut être envoyé vers n’importe quel serveur de médiation du pool. Étant donné que la plupart des systèmes PBX IP ne prennent pas en charge l’équilibrage de charge DNS, nous vous recommandons de qu’individuelles connexions SIP directes défini dans le système IP-PBX pour chaque serveur de médiation du pool. Le système IP-PBX gère ensuite son propre équilibrage en répartissant le trafic sur le groupe de jonction. Il est supposé que le groupe de jonction a un ensemble cohérent de règles de routage à l’IP-PBX. Si tel IP-PBX prend en charge ce concept de groupe de jonction et comment il croise la redondance de IP-PBX propre et architecture de clustering doit être déterminée avant de déterminer si un cluster de serveur de médiation peut interagir correctement avec un système IP-PBX.
    
Un pool de serveurs de médiation doit avoir un affichage de la passerelle de pair avec lequel elle interagit uniform. Cela signifie que tous les membres du pool accèdent à la même définition de passerelle homologue à partir du magasin de configurations et qu’ils ont tous autant de chances d’interagir avec elle pour les appels sortants. Par conséquent, il n’existe aucun moyen de segment du pool afin que certains serveurs de médiation communiquer avec certains homologues de passerelle pour les appels sortants. Si ce segmentation est nécessaire, un pool de serveurs de médiation distinct doit être utilisé. Ce serait le cas, par exemple, si les fonctionnalités associées dans les passerelles RTC, jonctions SIP ou systèmes IP-PBX pour interagir avec un pool n’étaient pas présentes (voir plus haut dans cette rubrique).
  
Une passerelle PSTN, IP-PBX ou homologue de jonction SIP peut acheminer sur plusieurs serveurs de médiation ou jonctions. Le nombre de passerelles un pool de serveurs de médiation particulier peut contrôler varie selon le nombre d’appels qui utilisent le contournement de média. Si un grand nombre d’appels utilisent le contournement de média, un serveur de médiation du pool peuvent gérer plus grand nombre d’appels, car seul traitement de couche de signalisation est nécessaire. 
  
## <a name="call-admission-control-and-mediation-server"></a>Contrôle d’admission des appels et serveur de médiation

Le contrôle d’admission des appels (CAC) gère l’établissement de session en temps réel en tenant compte de la bande passante disponible pour éviter toute dégradation de la qualité de l’expérience (QoE) pour les utilisateurs sur des réseaux saturés. Pour ce faire, le serveur de médiation est responsable de la gestion de bande passante pour ses deux interactions sur le Skype côté serveur de l’entreprise et sur le côté de la passerelle. Dans le cadre du contrôle d’admission des appels, l’entité qui met fin à l’appel gère la réservation de la bande passante. Les homologues de passerelle (passerelle PSTN, IP-PBX, SBC) interagissant avec le serveur de médiation sur le côté de la passerelle ne prennent pas charge Skype pour le contrôle d’admission des appels Business Server. Par conséquent, le serveur de médiation doit gérer les interactions de bande passante part son homologue de passerelle. La mesure du possible, le serveur de médiation réserver à l’avance la bande passante. Si c’est impossible (par exemple, si la localité du point de terminaison multimédia final du côté passerelle est inconnue pour un appel sortant vers l’homologue de passerelle), la bande passante est réservée quand l’appel est passé. Ce comportement peut entraîner une sur-souscription de bande passante, mais c’est le seul moyen d’empêcher les sonneries factices.
  
La déviation du trafic multimédia et la réservation de bande passante s’excluent mutuellement. Si la déviation du trafic multimédia est utilisée pour un appel, le contrôle d’admission des appels n’est pas effectué pour cet appel. L’hypothèse repose sur le fait qu’aucun lien avec bande passante restreinte n’est impliqué dans l’appel. Si le contrôle d’admission des appels d’appel est utilisé pour un appel particulier qui implique le serveur de médiation, cet appel ne peut pas utiliser le contournement de média.
  
Pour plus d’informations sur les médias contournement de média ou contrôle d’admission des appels, voir [Plan pour le média de contournement dans Skype pour les entreprises](media-bypass.md) ou les [planifier le contrôle d’admission des appels d’appel dans Skype pour Business Server](call-admission-control.md).
  
## <a name="enhanced-9-1-1-e9-1-1-and-mediation-server"></a>Enhanced 9-1-1 (E9-1-1) et serveur de médiation

Le serveur de médiation possède des capacités étendues afin que qu’il puisse interagir correctement avec des fournisseurs de service Enhanced 9-1-1 (E9-1-1). Aucune configuration spéciale n’est nécessaire sur le serveur de médiation. Les extensions SIP requises pour l’interaction E9-1-1 sont, par défaut, inclus dans le protocole SIP du serveur de médiation pour ses interactions avec un homologue de passerelle (passerelle PSTN, IP-PBX ou le contrôleur SBC d’un fournisseur de services de téléphonie Internet, y compris Service E9-1-1 Fournisseurs)
  
Si la jonction SIP vers un fournisseur de services E9-1-1 peut être arrêtée sur un pool de serveur de médiation existant ou nécessite des serveurs de médiation autonome dépendent si le contrôleur SBC E9-1-1 peut interagir avec un pool de serveurs de médiation. Pour plus d’informations, voir [jonction m : n dans Skype pour Business Server](m-n-trunk.md).
  
## <a name="media-bypass-and-mediation-server"></a>Déviation du trafic multimédia et serveur de médiation

Le contournement de média est un Skype pour la fonctionnalité Business Server qui permet à un administrateur de configurer le routage des appels pour le flux directement entre le point de terminaison utilisateur et la passerelle de réseau téléphonique commuté sans parcourir le serveur de médiation. Le contournement de média améliore la qualité des appels en réduisant la latence, traduction inutile, les risques de perte de paquets et le nombre de points de défaillance potentiels. Lorsqu’un site distant sans serveur de médiation est connecté à un site central par un ou plusieurs liaisons réseau étendu à bande passante restreinte, le contournement de média réduit les besoins en bande passante en activant le média à partir d’un client sur un site distant directement à la passerelle locale sans tout d’abord avoir flux WAN lier à un serveur de médiation sur le site central et sauvegarder. Cette réduction dans le traitement des médias également complète permet de contrôler plusieurs passerelles le serveur de médiation.
  
La déviation du trafic multimédia et le contrôle d’admission des appels s’excluent mutuellement. Si la déviation du trafic multimédia est utilisée pour un appel, le contrôle d’admission des appels n’est pas effectué pour cet appel. L’hypothèse repose sur le fait qu’aucun lien avec bande passante restreinte n’est impliqué dans l’appel.
  
## <a name="topologies-for-mediation-server"></a>Topologies du serveur de médiation

Par défaut le Skype pour Business Server, serveur de médiation est colocalisé avec un serveur Standard Edition, un pool frontal ou serveur Survivable Branch Appliance. Tous les serveurs de médiation dans un pool frontal doit être configurés de façon identique.
  
Où les performances sont un problème, il peut être préférable de déployer un ou plusieurs serveurs de médiation dans un pool autonome dédié. Nous vous conseillons absolument un pool autonome si vous déployez une jonction SIP. 
  
Si vous déployez des connexions SIP directes à une passerelle PSTN complet qui prend en charge le contournement de média et de charge DNS l’équilibrage, un serveur de médiation autonome pool n’est pas nécessaire. Il s’agit, car les passerelles qualifiées sont capables de charge DNS équilibrée à un pool de serveurs de médiation et qu’ils peuvent recevoir du trafic de n’importe quel serveur de médiation dans un pool.
  
Nous vous recommandons également de colocaliser le serveur de médiation sur un pool frontal lorsque vous avez déployé l’IP-PBX ou vous connecter à d’un serveur de fournisseur de téléphonie Internet contrôleur de Session bordure (SBC), dans la mesure où une des conditions suivantes sont remplie :
  
- L’IP-PBX ou SBC est configuré pour recevoir du trafic de n’importe quel serveur de médiation du pool et peut acheminer le trafic de manière uniforme sur tous les serveurs de médiation du pool.
    
- Le système IP-PBX ne prend pas en charge le contournement de média, mais le pool frontal qui héberge le serveur de médiation peut gérer le transcodage vocal des appels qui ne s’applique pas le contournement de média non.
    
Vous pouvez utiliser Microsoft Lync Server 2013, outil de planification pour déterminer si le pool frontal où vous voulez colocaliser le serveur de médiation peut gérer la charge. Si votre environnement ne peut pas ces exigences, vous devez déployer un pool de serveur de médiation autonome.
  
La figure suivante montre une topologie simple constituée de deux sites connectés par une liaison de réseau étendu. Serveur de médiation est colocalisé sur un pool frontal sur Site 1. Les serveurs de médiation sur Site 1 contrôle la passerelle PSTN sur Site 1 et la passerelle sur Site 2. Dans cette topologie, la déviation du trafic multimédia est activée globalement afin d’utiliser les informations de site et de région, et le contournement est activé sur les jonctions vers chaque passerelle RTC (GW1 et GW2).
  
**Exemple de sites connectés par une liaison de réseau étendu avec un serveur de médiation pour Site 1 et une passerelle RTC pour Site 2**

![Topologie vocale avec passerelle WAN de serveur de médiation](../../media/Plan_LyncServer_Voice_Topo_MedSvrWanGwy.jpg)
  
La figure suivante illustre une topologie simple où le serveur de médiation est colocalisé sur le pool frontal sur Site 1 et dispose d’une connexion SIP Direct à l’IP-PBX sur Site 1. Dans cette illustration, le serveur de médiation contrôle également une passerelle PSTN sur Site 2. Supposons que Skype pour les utilisateurs professionnels existe au niveau de Sites 1 et 2. Supposons également que le système IP-PBX doté d’un processeur média associé qui doit être parcouru par tous les composants multimédia provenant de Skype pour systèmes d’extrémité métiers avant d’être envoyés aux points de terminaison multimédia contrôlés par le système IP-PBX. Dans cette topologie, la déviation du trafic multimédia est activée globalement pour utiliser les informations de site et de région, et il est activé pour les jonctions vers la passerelle PBX et RTC.
  
**Exemple de sites connectés par une liaison de réseau étendu avec un serveur de médiation pour Site 1 et un PBX pour Site 2**

![Vocale PBX WAN de topologie Mediation Server](../../media/Plan_LyncServer_Voice_Topo_MedSvrWanPbx.jpg)
  
La dernière figure dans cette rubrique illustre une topologie où le serveur de médiation est connecté à la SBC d’un fournisseur de services de téléphonie Internet. 
  
## <a name="planning-decisions-for-mediation-server"></a>Décisions de planification relatives au serveur de médiation

Cette rubrique décrit les décisions de planification que vous devez faire pour votre déploiement de serveur de médiation,
  
### <a name="collocated-or-stand-alone-mediation-server"></a>Serveur de médiation colocalisé ou autonome ?

Par défaut le serveur de médiation est colocalisé sur le serveur Standard Edition server ou un serveur frontal dans un pool frontal sur les sites centraux. Le nombre d’appels RTC (réseau téléphonique commuté) pouvant être gérés et le nombre d’ordinateurs requis dans le pool dépendront des éléments suivants :
  
- Le nombre d’homologues de passerelle que le pool de serveur de médiation contrôle
    
- des périodes de trafic aux heures de pointe via ces passerelles ;
    
- Le pourcentage d’appels qui contournent le serveur de médiation
    
Lors de la planification, veillez à prendre en compte le support de traitement des exigences relatives aux appels PSTN et A / vidéoconférences qui ne sont pas configurés pour le média de contournement, ainsi que le traitement nécessaire pour gérer les interactions de signalisation pour le nombre d’heures de disponibilité appels qui doivent prise en charge. Si vous n’est pas suffisamment UC, vous devez déployer un pool de serveurs de médiation ; autonome et les passerelles PSTN, PBX IP et SBC sont besoin à diviser en sous-ensembles sont contrôlés par les serveurs de médiation colocalisé dans un pool et les serveurs de médiation autonome dans un ou plusieurs pools autonomes.
  
Si vous avez déployé des passerelles PSTN, IP-PBX ou contrôleurs de frontière de Session (SBC) qui ne prennent pas en charge les fonctionnalités correctes pour interagir avec un pool de serveurs de médiation, notamment les suivants, puis ils devront être associé à un pool autonome composé d’un seul serveur de médiation :
  
- Effectuer le nom de domaine DNS (Domain Name System) équilibrage entre les serveurs de médiation dans un pool de la couche réseau (ou bien acheminer le trafic de manière uniforme sur tous les serveurs de médiation dans un pool)
    
- Accepter le trafic à partir de n’importe quel serveur de médiation dans un pool
    
Vous pouvez utiliser le Microsoft Lync Server 2013, outil de planification pour évaluer si colocaliser le serveur de médiation avec votre pool frontal peut gérer la charge. Si votre environnement ne peut pas ces exigences, vous devez déployer un pool de serveur de médiation autonome.
  
### <a name="central-site-and-branch-site-considerations"></a>Aspects relatifs au site central et aux sites de succursale

 Serveurs de médiation sur le site central peuvent servir à acheminer les appels pour IP-PBX ou des passerelles PSTN au niveau des sites de succursale. Toutefois, si vous déployez les jonctions SIP, vous devez déployer un serveur de médiation au niveau du site dans lequel chaque jonction se termine. Ayant un serveur de médiation au niveau du site central acheminer les appels d’un système IP-PBX ou d’une passerelle PSTN sur un site de succursale ne nécessite pas l’utilisation de supports de contournement. Cependant, si vous pouvez l’activer, vous pourrez réduire la latence du chemin d’accès des médias et améliorer la qualité des médias car le chemin d’accès des médias n’est plus nécessaire pour suivre le chemin de signalisation. Le contournement de média réduit également la charge de traitement sur le pool.
  
> [!NOTE]
> La déviation du trafic multimédia ne fonctionnera pas avec chaque passerelle RTC, système IP-PBX et SBC. Microsoft a testé une série de passerelles RTC et de SBC avec l’aide de partenaires agréés et a réalisé des tests avec les systèmes IP-PBX de Cisco. Le contournement de média est pris en charge uniquement avec les produits et les versions répertoriés au [Unified Communications programme Open Interoperability - Lync Server](https://go.microsoft.com/fwlink/p/?LinkId=268730). 
  
Si la résilience de site de succursale est requise, un Survivable Branch Appliance ou une combinaison d’un serveur frontal, un serveur de médiation et une passerelle doit être déployé sur le site de succursale. (En partant du principe avec résilience de site de succursale est que de présence et de conférence ne sont pas résistantes au niveau du site.) Pour obtenir des instructions sur le site de succursale planification de voix, voir [Plan for Enterprise Voice resiliency dans Skype pour Business Server](enterprise-voice-resiliency.md).
  
Pour interagir avec un PBX IP, si le système IP-PBX ne prend pas correctement en charge les interactions multimédias au plus tôt avec plusieurs boîtes de dialogue préliminaires et interactions RFC 3960, il peut y avoir écrêtage du premier premiers mots pour les appels entrants à partir de l’IP-PBX à Skype pour le message d’accueil Points de terminaison d’entreprise. Ce problème peut être plus grave si un serveur de médiation sur un site central est routage des appels pour un IP-PBX où l’itinéraire s’arrête sur un site de succursale, car davantage de temps est nécessaire pour la signalisation à effectuer. Si vous rencontrez ce problème, déployez un serveur de médiation sur le site de succursale est la seule façon de réduire le découpage de la première premiers mots.
  
Enfin, si votre site central a un système PBX TDM, ou si votre système IP-PBX n’élimine pas la nécessité d’une passerelle PSTN, vous devez déployer une passerelle sur l’itinéraire d’appel de connexion du serveur de médiation et le système PBX.
  
> [!NOTE]
> Pour améliorer les performances multimédias d’un serveur de médiation autonome, activez RSS (Receive-Side Scaling) sur les cartes réseau de ces serveurs. RSS permet la gestion en parallèle des paquets entrants par plusieurs processeurs sur le serveur. Pour plus d’informations, voir [« côté réception mise à l’échelle améliorations dans Windows Server »](https://go.microsoft.com/fwlink/p/?LinkId=268731). Pour plus d’informations sur l’activation de RSS, reportez-vous à la documentation de votre carte réseau. 
  

