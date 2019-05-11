---
title: Jonction SIP dans Skype pour Business Server
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
ms.assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
description: En savoir plus sur l’acheminement SIP dans Skype pour Business Server Enterprise Voice
ms.openlocfilehash: a2b19010a3727e4dd7081b868118d27bbc3e1f68
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33913440"
---
# <a name="sip-trunking-in-skype-for-business-server"></a>Jonction SIP dans Skype pour Business Server

En savoir plus sur l’acheminement SIP dans Skype pour Business Server Enterprise Voice

Le protocole SIP (Session Initiation Protocol) sert à initier et à gérer les sessions de communications Voix sur IP (VoIP) pour le service téléphonique de base et d’autres services de communication en temps réel, tels que messagerie instantanée, conférence, détection de présence et multimédia. Cette section fournit des informations de planification pour l’implémentation de jonctions SIP, un type de connexion SIP qui s’étend au-delà des limites de votre réseau local.

## <a name="what-is-sip-trunking"></a>Qu’est-ce que la jonction SIP ?

Une jonction SIP est une connexion IP qui établit un lien de communications SIP entre votre organisation et un fournisseur de services de téléphonie Internet (ITSP) à l’extérieur de votre pare-feu. En règle générale, une jonction SIP permet de connecter un site central de votre organisation à un fournisseur ITSP. Dans certains cas, vous pouvez également décider d’utiliser la jonction SIP pour connecter votre site de succursale à un fournisseur de services de téléphonie Internet (ITSP).

Déployer l’acheminement SIP peut être une grande étape vers simplification de télécommunications de votre organisation et la préparation d’améliorations de la mise à jour pour les communications en temps réel. Un des principaux avantages d’une jonction SIP est que vous pouvez consolider les connexions de votre organisation pour le réseau téléphonique commuté (RTC) à un site central, au lieu de son prédécesseur, heure division multiplexing (TDM) acheminement, qui généralement nécessite une jonction distincte à partir de chaque site de succursale.

### <a name="cost-savings"></a>Économies

Les économies associées à la jonction SIP peuvent être substantielles :

- Les appels longue distance coûtent en général moins cher via une jonction SIP.

- Vous pouvez réduire les coûts de gestion et la complexité du déploiement.

- Les coûts d’accès de base (Basic rate interface, BRI) et d’accès primaire (Primary Rate Interface, PRI) sont éliminés si vous connectez une jonction SIP directement à votre fournisseur de services de téléphonie Internet pour un coût nettement plus bas. Avec une jonction TDM, les fournisseurs de service facturent les appels à la minute. Le coût d’une jonction SIP peut être basé sur l’utilisation de la bande passante, que vous pouvez acheter en plus petites tranches plus économiques. (Le coût réel dépend du modèle de service du fournisseur de services de téléphonie Internet que vous choisissez.)

#### <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a>Jonction SIP comparée à l’hébergement d’une passerelle RTC ou d’un PBX IP

Étant donné que les jonctions SIP se connectent directement à votre fournisseur de service, vous pouvez éliminer les passerelles RTC et éviter le coût et la complexité de leur gestion. L’utilisation d’une jonction SIP peut se traduire par des économies substantielles, car les tâches de maintenance et d’administration sont réduites.

### <a name="expanded-voip-services"></a>Services VoIP étendus

Bénéficier de fonctionnalités vocales est souvent la principale motivation pour déployer une jonction SIP, mais la prise en charge de fonctionnalités vocales n’est que la première étape. Avec l’acheminement SIP, vous pouvez étendre les fonctionnalités VoIP et activer Skype pour Business Server fournir un ensemble plus riche de services. Par exemple :

- Détection de présence enrichie pour les périphériques qui n’exécutent pas Skype pour Business Server peut permettre une meilleure intégration des téléphones mobiles, ce qui vous permet de voir lorsqu’un utilisateur est occupé sur un téléphone mobile.

- L’appel d’urgence E9-1-1 permet les secours qui répondent aux 911 appels pour déterminer l’emplacement de l’appelant à partir de son numéro de téléphone.

> [!NOTE]
> Contactez votre fournisseur de services de téléphonie Internet pour savoir quels services il prend en charge et peut activer pour votre organisation.

### <a name="sip-trunks-vs-direct-sip-connections"></a>Différences entre les jonctions SIP et les connexions SIP directes

Le terme jonction est dérivé de la technologie de commutation. Il fait référence à une ligne physique dédiée qui connecte les équipements téléphoniques de commutation. Comme son prédécesseur, multiplexage temporel jonctions (TDM), jonctions SIP sont des connexions entre deux réseaux distincts de SIP — le Skype pour enterprise Business Server et ce dernier. Contrairement aux jonctions de commutation, les jonctions SIP sont des connexions virtuelles pouvant être établies sur n’importe quel type de connexion de jonction SIP pris en charge.

En revanche, les connexions SIP directes sont des connexions SIP qui ne franchissent pas les limites du réseau local (c’est-à-dire qu’elles se connectent à une passerelle RTC ou à un PBX dans votre réseau interne). Pour plus d’informations sur la façon dont vous pouvez utiliser des connexions SIP directes avec Skype pour Business Server, voir [connexions SIP directes dans Skype pour Business Server](direct-sip.md).

## <a name="how-do-i-implement-sip-trunking"></a>Implémentation d’une jonction SIP

Pour implémenter la jonction SIP, vous devez acheminer la connexion via un serveur de médiation, qui agit en tant que proxy pour les sessions de communication entre Skype pour les clients Business Server et le fournisseur de services et convertit multimédia, lorsque cela est nécessaire.

Chaque serveur de médiation a une interface réseau interne et un réseau externe. L’interface interne se connecte à des serveurs frontaux. L’interface externe est généralement appelé l’interface de passerelle car il a été généralement utilisé pour connecter le serveur de médiation à une passerelle de réseau téléphonique commuté ou un IP-PBX. Pour implémenter une jonction SIP, vous connecter à l’interface externe du serveur de médiation au composant de périmètre externe de ce dernier. Ce dernier peut être un contrôleur de session en périphérie (SBC), un routeur ou une passerelle.

Pour plus d’informations sur les serveurs de médiation, voir [composant serveur de médiation dans Skype pour Business Server](mediation-server.md).

### <a name="centralized-vs-distributed-sip-trunking"></a>Comparatif entre jonction SIP centralisée et jonction SIP distribuée

L’acheminement SIP centralisée achemine tout le trafic VoIP, y compris le trafic de site de succursale, par le biais de votre site central. Le modèle de déploiement centralisé est simple, rentable et est généralement l’approche recommandée pour l’implémentation de jonctions SIP avec Skype pour Business Server.

Jonction SIP distribuée est un modèle de déploiement dans lesquels vous implémentez des jonctions SIP locales à un ou plusieurs sites de succursale. Le trafic VoIP est ensuite acheminé à partir du site de succursale directement à un fournisseur de services sans passer par le site central.

La jonction SIP distribuée n’est requise que dans les cas suivants :

- Le site de succursale requiert une connectivité survivable téléphone (par exemple, si le réseau étendu tombe en panne). Cette exigence doit être analysée pour chaque site de succursale ; certains de vos branches peuvent nécessiter la redondance et basculement, tandis que d’autres ne peuvent pas.

- Résistance est requise entre deux sites centraux. Vous devez vous assurer qu’une jonction SIP se termine à chaque site central. Par exemple, si vous avez des sites centraux Dublin et Tukwila et deux utilisent la jonction SIP d’un seul site, si la jonction tombe en panne, les autres utilisateurs du site ne peut pas émettre des appels de RTC.

- Le site de succursale et le site central sont dans différents pays/régions. Pour des raisons de compatibilité et légales, vous devez disposer d’au moins une jonction SIP par pays/région. Par exemple, dans l’Union Européenne, les communications ne peuvent pas sortir d’un pays ou d’une région sans terminaison locale à un point centralisé.

Selon l’emplacement géographique des sites et la quantité de trafic que vous prévoyez au sein de votre entreprise, vous ne souhaitez pas acheminer tous les utilisateurs par le biais de la jonction SIP centrale, ou vous pouvez choisir d’acheminer certains utilisateurs via une jonction SIP sur leur site de succursale. Pour vous aider à établir vos besoins, répondez aux questions suivantes :

- Quelle est la chaque site (autrement dit, combien d’utilisateurs est activés pour Enterprise Voice) ?

- Quels numéros de Sélection directe à l’arrivée (SDA) reçoivent le plus grand nombre d’appels sur chaque site ?

La décision d’opter pour une jonction SIP centralisée ou distribuée doit être basée sur une analyse des coûts-avantages. Dans certains cas, il peut être plus avantageux d’opter pour un modèle de déploiement distribué, même s’il n’est pas nécessaire. Dans un déploiement complètement centralisé, tout le trafic site de succursale est acheminé via des liaisons WAN. Au lieu de payer pour la bande passante requise pour la liaison de réseau étendu, il est peut-être préférable d’utiliser une jonction SIP distribuée. Par exemple, vous pouvez choisir de déployer un serveur Standard Edition server sur un site de succursale fédération vers le site central, ou vous souhaiterez peut-être déployer un serveur Survivable Branch Appliance ou un serveur Survivable Branch Server avec une passerelle de petite taille.

> [!NOTE]
> Pour plus d’informations sur l’acheminement SIP distribué, voir [l’acheminement SIP dans Skype pour Business Server Branch site](branch-site.md).

### <a name="supported-sip-trunking-connection-types"></a>Types de connexion de jonction SIP pris en charge

Skype pour Business Server prend en charge les types suivants de la connexion de jonction SIP :

- Le réseau privé MPLS (Multiprotocol Label Switching) dirige et transporte les données d’un nœud du réseau vers le suivant. La bande passante dans un réseau MPLS est partagée avec d’autres abonnés, et chaque paquet de données est affecté une étiquette pour distinguer les données d’un abonné à partir d’une autre personne. Ce type de connexion ne requiert pas de réseau privé virtuel (VPN). Un des inconvénients possibles est que le trafic IP excessif peut interférer avec le trafic VoIP à moins qu’une priorité soit affectée au trafic VoIP.

- Une connexion privée sans autre trafic, par exemple, une connexion à fibre optique louée ou une ligne T1, est généralement le type de connexion le plus fiable et le plus sûr. En effet, elle offre la capacité la plus élevée en matière de transport des appels. Cependant, elle est généralement plus chère. Un VPN n’est pas nécessaire. Les connexions privées sont adaptées aux organisations à grands volumes d’appels ou soumises à des exigences strictes en matière de sécurité et de disponibilité.

- Internet est le type de connexion le moins cher, mais aussi le moins fiable. Connexion Internet est la seule Skype pour Business Server SIP acheminement type de connexion nécessitant VPN.

#### <a name="selecting-a-connection-type"></a>Sélection d’un type de connexion

Le type de connexion de jonction SIP le plus approprié à votre entreprise dépend de vos besoins et de votre budget.

- Pour les grandes et moyennes entreprises, un réseau MPLS offre en général la meilleure valeur. Il est capable de fournir la bande passante nécessaire à un tarif moindre qu’un réseau privé spécialisé.

- Pour les grandes entreprises, une connexion privée à fibre optique, T1, T3 ou supérieure (E1, E3 ou supérieure dans l’Union Européenne) peut être adaptée.

- Pour une petite entreprise ou un site de succursale avec le volume d’appels faible, l’acheminement SIP via Internet peut être la meilleure solution. Ce type de connexion n’est pas recommandé pour les sites de taille moyenne ou de grande taille.

### <a name="bandwidth-requirements"></a>Bande passante requise

La capacité d’appels (c’est-à-dire le nombre d’appels simultanés devant être pris en charge) détermine la bande passante requise pour votre implémentation. Vous devez prendre en compte la disponibilité de la bande passante pour pouvoir tirer parti de la capacité maximale facturée. Calculez vos besoins en bande passante de jonction SIP maximale à l’aide de la formule suivante :

Bande passante de jonction SIP maximale = Nbre max. d’appels simultanés (64 Kbits/s + taille d’en-tête)

> [!NOTE]
> La taille d’en-tête maximale est de 20 octets.

### <a name="codec-support"></a>Prise en charge de codec

Skype pour Business Server prend en charge uniquement les codecs suivants :

- G.711 a-law (utilisé principalement en dehors de l’Amérique du Nord)

- G.711 µ-law (utilisé en Amérique du Nord)

### <a name="internet-telephony-service-provider"></a>Fournisseur de services de téléphonie Internet

La manière dont vous mettez en œuvre le côté fournisseur de services d’une connexion de jonction SIP varie d’un fournisseur de services de téléphonie Internet à l’autre. Pour plus d’informations sur le déploiement, contactez votre fournisseur de services. Pour obtenir la liste des fournisseurs de services de jonction SIP certifiés, voir le [site Web Microsoft Unified Communications programme Open Interoperability](https://go.microsoft.com/fwlink/p/?LinkId=287029).

Pour plus d’informations sur les fournisseurs de jonctions SIP approuvés par Microsoft, contactez votre représentant Microsoft.

> [!IMPORTANT]
> Vous devez utiliser un fournisseur de services approuvé par Microsoft pour garantir que votre fournisseur de services de téléphonie Internet prend en charge toutes les fonctionnalités qui transitent par la jonction SIP (par exemple, la configuration et la gestion des sessions et la prise en charge des services VoIP étendus). Le support technique Microsoft ne s’étend pas aux configurations qui utilisent des fournisseurs non approuvés. Si vous utilisez actuellement un fournisseur de services Internet non approuvé pour la jonction SIP, vous pouvez envisager de continuer à utiliser ce fournisseur en tant que FAI et utiliser un fournisseur approuvé par Microsoft pour la jonction SIP.

### <a name="topologies-and-components-for-sip-trunking"></a>Topologies et composants de jonction SIP

La figure suivante illustre la topologie d’acheminement SIP dans Skype pour Business Server.

**Topologie de jonction SIP**

![Topologie de jonction SIP](../../media/669fb55d-7c81-4e21-9421-fabc43d6e064.jpg)

Comme le montre le diagramme, un réseau privé virtuel (VPN) IP est utilisé pour la connectivité entre le réseau d’entreprise et le fournisseur de services de réseau téléphonique commuté. L’objectif de ce réseau privé est de fournir la connectivité IP, d’améliorer la sécurité et (éventuellement) d’obtenir des garanties de qualité de service. En raison de la nature d’un VPN, vous n’avez pas besoin d’utiliser TLS pour le trafic de signalisation SIP, ni SRTP pour le trafic multimédia. De ce fait, les connexions entre l’entreprise et le fournisseur de services consistent en des connexions TCP ordinaires pour SIP et des connexions RTP ordinaires (avec le protocole UDP) pour les médias traités par tunnel via un réseau VPN IP. Veillez à ce que tous les pare-feu situés entre les routeurs VPN disposent de ports ouverts pour permettre aux routeurs VPN de communiquer. Par ailleurs, les adresses IP des périmètres externes des routeurs VPN doivent être publiquement routables.

> [!IMPORTANT]
> Contactez votre fournisseur de services pour déterminer s’il fournit la prise en charge pour la disponibilité élevée, notamment le basculement. Si c’est le cas, vous devrez déterminer les procédures pour la configurer. Par exemple, vous devez ne configurer qu’une seule adresse IP et une jonction SIP sur chaque serveur de médiation, ou avez-vous besoin configurer plusieurs jonctions SIP sur chaque serveur de médiation ? > si vous avez plusieurs sites centraux, demandez également si le fournisseur de services a la possibilité d’activer les connexions vers et à partir d’un autre site central.

> [!NOTE]
> Pour la jonction SIP, nous vous recommandons vivement de déployer les serveurs de médiation autonome. Pour plus d’informations, reportez-vous à [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx) dans la documentation de déploiement.

### <a name="securing-the-mediation-server-for-sip-trunking"></a>Sécurisation du serveur de médiation pour la jonction SIP

Pour des raisons de sécurité, vous devriez configurer un réseau local virtuel (VLAN) pour chaque connexion entre deux routeurs VPN. Le processus courant de configuration d’un VLAN varie d’un fabricant de routeur à l’autre. Pour plus d’informations, contactez le fournisseur de votre routeur.

Nous vous conseillons de suivre les directives suivantes :

- La valeur d’un réseau local virtuel (VLAN) entre le serveur de médiation et le routeur VPN dans le réseau de périmètre (également appelé zone DMZ, zone démilitarisée et sous-réseau filtré).

- N’autorisez pas le transfert des paquets de diffusions ou de multidiffusions entre le routeur et le réseau local virtuel.

- Bloquer les règles de routage qui acheminent le trafic du routeur vers n’importe où, mais le serveur de médiation.

Si vous utilisez un serveur VPN, bous vous conseillons de suivre les directives suivantes :

- Configurer un réseau local virtuel entre le serveur VPN et le serveur de médiation.

- N’autorisez pas la transmission des paquets de diffusions ou de multidiffusions du serveur VPN vers le réseau local virtuel.

- Bloquez toute règle de routage qui achemine le trafic du serveur VPN vers n’importe où, mais le serveur de médiation.

- Chiffrez les données sur le réseau privé virtuel (VPN) à l’aide de l’encapsulation générique de routage (GRE).

## <a name="see-also"></a>Voir aussi

[Acheminement SIP dans Skype pour Business Server Branch site](branch-site.md)

