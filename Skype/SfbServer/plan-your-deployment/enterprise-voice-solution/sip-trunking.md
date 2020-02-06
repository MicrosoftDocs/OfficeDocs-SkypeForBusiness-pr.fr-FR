---
title: Trunking SIP dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
description: En savoir plus sur le trunking SIP dans Skype entreprise Server Voice
ms.openlocfilehash: 229774ef976a08031da7892dec0088d78b954b24
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802414"
---
# <a name="sip-trunking-in-skype-for-business-server"></a>Trunking SIP dans Skype entreprise Server

En savoir plus sur le trunking SIP dans Skype entreprise Server Voice

Le protocole SIP (Session Initiation Protocol) sert à initier et à gérer les sessions de communications Voix sur IP (VoIP) pour le service téléphonique de base et d’autres services de communication en temps réel, tels que messagerie instantanée, conférence, détection de présence et multimédia. Cette section fournit des informations de planification pour l’implémentation de jonctions SIP, un type de connexion SIP qui s’étend au-delà des limites de votre réseau local.

## <a name="what-is-sip-trunking"></a>Qu’est-ce que la jonction SIP ?

Une jonction SIP est une connexion IP qui établit un lien de communications SIP entre votre organisation et un fournisseur de services de téléphonie Internet (ITSP) à l’extérieur de votre pare-feu. En règle générale, un Trunk SIP est utilisé pour connecter le site central de votre organisation à un ITSP. Dans certains cas, vous pouvez également décider d’utiliser la jonction SIP pour connecter votre site de succursale à un fournisseur de services de téléphonie Internet (ITSP).

Le déploiement du trunking SIP peut être une étape importante de la simplification de la communication de votre organisation et de la préparation des améliorations à la date apportées aux communications en temps réel. L’un des principaux avantages du trunking SIP est que vous pouvez consolider les connexions de votre organisation au réseau téléphonique commuté (PSTN) sur un site central, par opposition à son prédécesseur de trunking de répartition du temps (TDM), qui est généralement Il est nécessaire de disposer d’un Trunk distinct depuis chaque site de succursale.

### <a name="cost-savings"></a>Économies

Les économies associées à la jonction SIP peuvent être substantielles :

- Les appels longue distance coûtent en général moins cher via une jonction SIP.

- Vous pouvez réduire les coûts de gestion et la complexité du déploiement.

- Les coûts d’accès de base (Basic rate interface, BRI) et d’accès primaire (Primary Rate Interface, PRI) sont éliminés si vous connectez une jonction SIP directement à votre fournisseur de services de téléphonie Internet pour un coût nettement plus bas. Avec une jonction TDM, les fournisseurs de service facturent les appels à la minute. Le coût d’une jonction SIP peut être basé sur l’utilisation de la bande passante, que vous pouvez acheter en plus petites tranches plus économiques. (Le coût réel dépend du modèle de service du fournisseur de services de téléphonie Internet que vous choisissez.)

#### <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a>Jonction SIP comparée à l’hébergement d’une passerelle RTC ou d’un PBX IP

Étant donné que les jonctions SIP se connectent directement à votre fournisseur de service, vous pouvez éliminer les passerelles RTC et éviter le coût et la complexité de leur gestion. L’utilisation d’une jonction SIP peut se traduire par des économies substantielles, car les tâches de maintenance et d’administration sont réduites.

### <a name="expanded-voip-services"></a>Services VoIP étendus

Bénéficier de fonctionnalités vocales est souvent la principale motivation pour déployer une jonction SIP, mais la prise en charge de fonctionnalités vocales n’est que la première étape. Le trunking SIP vous permet d’étendre les fonctionnalités VoIP et d’activer Skype entreprise Server pour offrir un ensemble de services plus riche. Par exemple :

- La détection améliorée de la présence des appareils qui n’exécutent pas Skype entreprise Server peut offrir une meilleure intégration aux téléphones mobiles, ce qui vous permet de voir quand un utilisateur se trouve sur un téléphone mobile.

- Les appels d’urgence E9-1-1 permettent aux autorités qui répondent aux appels 911 de déterminer l’emplacement de l’appelant sur son numéro de téléphone.

> [!NOTE]
> Contactez votre fournisseur de services de téléphonie Internet pour savoir quels services il prend en charge et peut activer pour votre organisation.

### <a name="sip-trunks-vs-direct-sip-connections"></a>Différences entre les jonctions SIP et les connexions SIP directes

Le terme jonction est dérivé de la technologie de commutation. Il fait référence à une ligne physique dédiée qui connecte les équipements téléphoniques de commutation. Comme leur prédécesseur, les Trunks de répartition du temps (TDM), les Trunks SIP sont des connexions entre deux réseaux SIP distincts : Skype entreprise Server Enterprise et ITSP. Contrairement aux jonctions de commutation, les jonctions SIP sont des connexions virtuelles pouvant être établies sur n’importe quel type de connexion de jonction SIP pris en charge.

En revanche, les connexions SIP directes sont des connexions SIP qui ne franchissent pas les limites du réseau local (c’est-à-dire qu’elles se connectent à une passerelle RTC ou à un PBX dans votre réseau interne). Pour plus d’informations sur l’utilisation des connexions SIP directes avec Skype entreprise Server, reportez-vous à la rubrique [connexions SIP directes dans Skype entreprise Server](direct-sip.md).

## <a name="how-do-i-implement-sip-trunking"></a>Implémentation d’une jonction SIP

Pour implémenter le trunking SIP, vous devez Router la connexion à l’aide d’un serveur de médiation, qui fait office de proxy pour les sessions de communication entre les clients Skype entreprise Server et le prestataire de services et transcode le média, si nécessaire.

Chaque serveur de médiation possède une interface réseau interne et une interface réseau externe. L’interface interne se connecte aux serveurs frontaux. L’interface externe est généralement appelée interface de la passerelle, car elle a traditionnellement été utilisée pour connecter le serveur de médiation à une passerelle de réseau téléphonique commuté (PSTN) ou un PBX IP. Pour implémenter une ligne SIP, vous connectez l’interface externe du serveur de médiation au composant de bord externe du ITSP. Ce dernier peut être un contrôleur de session en périphérie (SBC), un routeur ou une passerelle.

Pour plus d’informations sur les serveurs de médiation, voir [composant serveur de médiation dans Skype entreprise Server](mediation-server.md).

### <a name="centralized-vs-distributed-sip-trunking"></a>Comparatif entre jonction SIP centralisée et jonction SIP distribuée

Le trunking SIP centralisé achemine tout le trafic VoIP, y compris le trafic du site de succursale, par le biais de votre site central. Le modèle de déploiement centralisé est simple, rentable et est généralement l’approche recommandée pour l’implémentation de lignes SIP avec Skype entreprise Server.

Le trunking SIP distribué est un modèle de déploiement dans lequel vous implémentez des Trunks SIP locaux sur un ou plusieurs sites de succursale. Le trafic VoIP est alors acheminé à partir du site de succursale directement vers un fournisseur de services, sans passer par le site central.

La jonction SIP distribuée n’est requise que dans les cas suivants :

- Le site de succursale nécessite une connectivité téléphonique plus Survivable (par exemple, si le réseau étendu monte en panne). Cette obligation doit être analysée pour chaque site de succursale ; Il est possible que certaines de vos succursales nécessitent une redondance et un basculement, alors que d’autres ne le sont pas.

- La résilience est requise entre deux sites centraux. Vous devez vous assurer qu’un Trunk SIP s’arrête sur chaque site central. Par exemple, si vous avez des sites centraux de Dublin et Tukwila et que vous utilisez uniquement le Trunk SIP d’un site, si le Trunk s’arrête, les utilisateurs du site ne peuvent pas passer d’appels RTC.

- Le site de succursale et le site central sont dans des pays/régions différents. Pour des raisons de compatibilité et légales, vous devez disposer d’au moins une jonction SIP par pays/région. Par exemple, dans l’Union Européenne, les communications ne peuvent pas sortir d’un pays ou d’une région sans terminaison locale à un point centralisé.

En fonction de l’emplacement géographique des sites et de la quantité de trafic que vous prévoyez au sein de votre entreprise, il est possible que vous ne souhaitiez pas acheminer tous les utilisateurs par le biais du réseau SIP central ou vous pouvez choisir de router des utilisateurs via une ligne SIP sur leur site de succursale. Pour vous aider à établir vos besoins, répondez aux questions suivantes :

- Quel est le niveau de chaque site (c’est-à-dire le nombre d’utilisateurs activés pour Enterprise Voice) ?

- Quels numéros de Sélection directe à l’arrivée (SDA) reçoivent le plus grand nombre d’appels sur chaque site ?

La décision d’opter pour une jonction SIP centralisée ou distribuée doit être basée sur une analyse des coûts-avantages. Dans certains cas, il peut être plus avantageux d’opter pour un modèle de déploiement distribué, même s’il n’est pas nécessaire. Dans un déploiement entièrement centralisé, le trafic de tous les sites de succursales est routé par le biais de liens WAN. Au lieu de payer pour la bande passante requise pour la liaison de réseau étendu, il est peut-être préférable d’utiliser une jonction SIP distribuée. Par exemple, vous pouvez choisir de déployer un serveur Standard Edition sur un site de succursale avec la Fédération sur le site central, ou vous pouvez déployer une application de succursale Survivable ou un serveur de succursales survivant avec une petite passerelle.

> [!NOTE]
> Pour plus d’informations sur le trunking SIP distribué, voir [trunking SIP site dans Skype entreprise Server](branch-site.md).

### <a name="supported-sip-trunking-connection-types"></a>Types de connexion de jonction SIP pris en charge

Skype entreprise Server prend en charge les types de connexion suivants pour le trunking SIP :

- Le réseau privé MPLS (Multiprotocol Label Switching) dirige et transporte les données d’un nœud du réseau vers le suivant. La bande passante d’un réseau MPLS est partagée avec d’autres abonnés, et chaque paquet de données est affecté d’une étiquette pour différencier les données d’un abonné d’une autre. Ce type de connexion ne requiert pas de réseau privé virtuel (VPN). Un des inconvénients possibles est que le trafic IP excessif peut interférer avec le trafic VoIP à moins qu’une priorité soit affectée au trafic VoIP.

- Une connexion privée sans autre trafic, par exemple, une connexion à fibre optique louée ou une ligne T1, est généralement le type de connexion le plus fiable et le plus sûr. En effet, elle offre la capacité la plus élevée en matière de transport des appels. Cependant, elle est généralement plus chère. Un VPN n’est pas nécessaire. Les connexions privées sont adaptées aux organisations à grands volumes d’appels ou soumises à des exigences strictes en matière de sécurité et de disponibilité.

- Internet est le type de connexion le moins cher, mais aussi le moins fiable. Connexion Internet est le seul type de connexion SIP de Skype entreprise Server qui nécessite un réseau privé virtuel (VPN).

#### <a name="selecting-a-connection-type"></a>Sélection d’un type de connexion

Le type de connexion de jonction SIP le plus approprié à votre entreprise dépend de vos besoins et de votre budget.

- Pour les grandes et moyennes entreprises, un réseau MPLS offre en général la meilleure valeur. Il est capable de fournir la bande passante nécessaire à un tarif moindre qu’un réseau privé spécialisé.

- Pour les grandes entreprises, une connexion privée à fibre optique, T1, T3 ou supérieure (E1, E3 ou supérieure dans l’Union Européenne) peut être adaptée.

- Dans le cas d’une petite entreprise ou d’un site de succursale avec un volume d’appel faible, le trunking SIP via Internet est le meilleur choix. Ce type de connexion n’est pas recommandé pour les sites de taille moyenne ou de grande taille.

### <a name="bandwidth-requirements"></a>Bande passante requise

La capacité d’appels (c’est-à-dire le nombre d’appels simultanés devant être pris en charge) détermine la bande passante requise pour votre implémentation. Vous devez prendre en compte la disponibilité de la bande passante pour pouvoir tirer parti de la capacité maximale facturée. Calculez vos besoins en bande passante de jonction SIP maximale à l’aide de la formule suivante :

Bande passante de jonction SIP maximale = Nbre max. d’appels simultanés (64 Kbits/s + taille d’en-tête)

> [!NOTE]
> La taille d’en-tête maximale est de 20 octets.

### <a name="codec-support"></a>Prise en charge de codec

Skype entreprise Server prend en charge uniquement les codecs suivants :

- G.711 a-law (utilisé principalement en dehors de l’Amérique du Nord)

- G.711 µ-law (utilisé en Amérique du Nord)

### <a name="internet-telephony-service-provider"></a>Fournisseur de services de téléphonie Internet

La manière dont vous mettez en œuvre le côté fournisseur de services d’une connexion de jonction SIP varie d’un fournisseur de services de téléphonie Internet à l’autre. Pour plus d’informations sur le déploiement, contactez votre fournisseur de services. Pour obtenir la liste des fournisseurs de services de trunking SIP certifiés, voir [site Web du programme d’interopérabilité Microsoft Unified Communications](https://go.microsoft.com/fwlink/p/?LinkId=287029).

Pour plus d’informations sur les fournisseurs de jonctions SIP approuvés par Microsoft, contactez votre représentant Microsoft.

> [!IMPORTANT]
> Vous devez utiliser un fournisseur de services approuvé par Microsoft pour garantir que votre fournisseur de services de téléphonie Internet prend en charge toutes les fonctionnalités qui transitent par la jonction SIP (par exemple, la configuration et la gestion des sessions et la prise en charge des services VoIP étendus). Le support technique Microsoft ne s’étend pas aux configurations qui utilisent des fournisseurs non approuvés. Si vous utilisez actuellement un fournisseur de services Internet non approuvé pour la jonction SIP, vous pouvez envisager de continuer à utiliser ce fournisseur en tant que FAI et utiliser un fournisseur approuvé par Microsoft pour la jonction SIP.

### <a name="topologies-and-components-for-sip-trunking"></a>Topologies et composants de jonction SIP

La figure suivante illustre la topologie de trunking SIP dans Skype entreprise Server.

**Topologie de trunking SIP**

![Topologie de jonction SIP](../../media/669fb55d-7c81-4e21-9421-fabc43d6e064.jpg)

Comme le montre le diagramme, un réseau privé virtuel (VPN) IP est utilisé pour la connectivité entre le réseau d’entreprise et le fournisseur de services de réseau téléphonique commuté. L’objectif de ce réseau privé est de fournir la connectivité IP, d’améliorer la sécurité et (éventuellement) d’obtenir des garanties de qualité de service. En raison de la nature d’un VPN, vous n’avez pas besoin d’utiliser TLS pour le trafic de signalisation SIP, ni SRTP pour le trafic multimédia. De ce fait, les connexions entre l’entreprise et le fournisseur de services consistent en des connexions TCP ordinaires pour SIP et des connexions RTP ordinaires (avec le protocole UDP) pour les médias traités par tunnel via un réseau VPN IP. Veillez à ce que tous les pare-feu situés entre les routeurs VPN disposent de ports ouverts pour permettre aux routeurs VPN de communiquer. Par ailleurs, les adresses IP des périmètres externes des routeurs VPN doivent être publiquement routables.

> [!IMPORTANT]
> Contactez votre fournisseur de services pour déterminer s’il fournit la prise en charge pour la disponibilité élevée, notamment le basculement. Si c’est le cas, vous devrez déterminer les procédures pour la configurer. Par exemple, avez-vous besoin de configurer une seule adresse IP et une ligne SIP Trunk sur chaque serveur de médiation, ou devez-vous configurer plusieurs ISL SIP sur chaque serveur de médiation ? > si vous avez plusieurs sites centraux, demandez-vous également si le prestataire de services peut activer les connexions à un autre site central.

> [!NOTE]
> Pour le trunking SIP, nous vous conseillons vivement de déployer des serveurs de médiation autonomes. Pour plus d’informations, reportez-vous à [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx) dans la documentation de déploiement.

### <a name="securing-the-mediation-server-for-sip-trunking"></a>Sécurisation du serveur de médiation pour la jonction SIP

Pour des raisons de sécurité, vous devriez configurer un réseau local virtuel (VLAN) pour chaque connexion entre deux routeurs VPN. Le processus courant de configuration d’un VLAN varie d’un fabricant de routeur à l’autre. Pour plus d’informations, contactez le fournisseur de votre routeur.

Nous vous conseillons de suivre les directives suivantes :

- Configurez un réseau local virtuel (VLAN) entre le serveur de médiation et le routeur VPN dans le réseau de périmètre (également appelé DMZ, zone démilitarisée et sous-réseau filtré).

- N’autorisez pas le transfert des paquets de diffusions ou de multidiffusions entre le routeur et le réseau local virtuel.

- Bloquez les règles de routage qui acheminent le trafic du routeur vers n’importe où, mais le serveur de médiation.

Si vous utilisez un serveur VPN, bous vous conseillons de suivre les directives suivantes :

- Configurez un VLAN entre le serveur VPN et le serveur de médiation.

- N’autorisez pas la transmission des paquets de diffusions ou de multidiffusions du serveur VPN vers le réseau local virtuel.

- Bloquer toutes les règles de routage qui routent le trafic du serveur VPN vers n’importe quel endroit, mais le serveur de médiation.

- Chiffrez les données sur le réseau privé virtuel (VPN) à l’aide de l’encapsulation générique de routage (GRE).

## <a name="see-also"></a>Voir aussi

[Trunking SIP site dans Skype entreprise Server](branch-site.md)

