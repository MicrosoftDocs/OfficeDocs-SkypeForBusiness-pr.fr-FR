---
title: Prise en charge des jonctions SIP dans Lync Server 2013
TOCTitle: Prise en charge des jonctions SIP
ms:assetid: e3042831-e8d8-4ea2-baa2-1a697401ffa0
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg399005(v=OCS.15)
ms:contentKeyID: 49299116
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Prise en charge des jonctions SIP dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Si vous envisagez d’utiliser Voix Entreprise avec un acheminement SIP, vous devez déployer un serveur de médiation et vérifier que les autres composants et infrastructure répondent aux conditions de prise en charge de votre modèle de déploiement. Pour plus d’informations sur le choix de mettre en œuvre un acheminement SIP, reportez-vous à [Vue d’ensemble d’une jonction SIP dans Lync Server 2013](lync-server-2013-overview-of-sip-trunking.md) (contenu éventuellement en anglais) dans la documentation relative à la planification.

Vous pouvez utiliser l’infrastructure de téléphonie d’entreprise de Microsoft Unified Communications Open Interoperability Program pour rechercher les passerelles RTC (réseau téléphonique commuté) qualifiées, les systèmes IP-PBX et les services de jonction SIP, dont les fournisseurs de services de téléphonie IP qualifiés. Pour plus d’informations, reportez-vous au site web de Microsoft Unified Communications Open Interoperability Program à l’adresse [http://go.microsoft.com/fwlink/p/?LinkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309).

## Prise en charge du serveur de médiation

Pour mettre en œuvre l’acheminement SIP, vous devez acheminer la connexion via un serveur de médiation qui agit comme un proxy pour les sessions de communication entre les clients Lync Server 2013 et le fournisseur de services. Le serveur de médiation décode le trafic multimédia provenant des clients et serveurs puis le réencode avant de l’envoyer au fournisseur de services. Ce réencodage est nécessaire, car les acheminements SIP ne prennent pas en charge certains codecs utilisés, comme la négociation de protocole Real Time Audio (RTA) ou Interactive Connectivity Establishment (ICE) pour la traversée du pare-feu.

Chaque serveur de médiation peut comporter deux cartes réseau, fournissant une interface réseau interne et externe. L’interface externe est appelée interface de passerelle, car elle sert généralement à se connecter à une passerelle RTC ou à un système IP-PBX. Pour mettre en œuvre un acheminement SIP, vous connectez l’interface externe à un contrôleur de session en périphérie (SBC) au niveau d’un fournisseur de services.

## Comparatif entre jonction SIP centralisée et jonction SIP distribuée

L’acheminement SIP *centralisé* achemine tout le trafic protocole voix sur IP (VoIP), dont le trafic du site de succursale, via votre centre de données. Le modèle de déploiement centralisé est simple, économique et constitue généralement la meilleure solution pour mettre en œuvre des acheminements SIP avec Lync Server 2013.

Selon les modèles d’utilisation de votre entreprise, vous pouvez choisir de ne pas acheminer tous les utilisateurs via un acheminement SIP centralisé. Pour vous aider à établir vos besoins, répondez aux questions suivantes :

  - Quelle est la taille de chaque site ? Combien y a-t-il d’utilisateurs ?

  - Quels numéros de Sélection directe à l’arrivée (SDA) reçoivent le plus grand nombre d’appels sur chaque site ?

La jonction SIP *distribuée* est un modèle de déploiement selon lequel vous mettez en œuvre une jonction SIP locale sur un ou plusieurs sites de succursale. Le trafic VoIP est ensuite acheminé à partir du site de succursale directement à son fournisseur de services, sans passer par votre centre de données.

La jonction SIP distribuée n’est requise que dans les cas suivants :

  - Le site de succursale nécessite une connectivité téléphonique de secours (par exemple, en cas de panne de la liaison de réseau étendu). Si la succursale n’a pas besoin d’une fonctionnalité de redondance et de basculement, le fournisseur de services facturera davantage et la configuration sera plus longue. Cette éventualité devrait être étudiée pour chaque site de succursale. Certaines de vos succursales peuvent nécessiter une redondance et un basculement, et d’autres non.

  - Le site de succursale et le centre de données sont situés dans différents pays/régions. Pour des raisons de compatibilité et légales, vous devez disposez d’au moins une jonction SIP par pays/région.

La décision d’opter pour une jonction SIP centralisée ou distribuée doit être basée sur une analyse des coûts-avantages. Dans certains cas, il peut être plus avantageux d’opter pour un mode de déploiement distribué, même s’il n’est pas nécessaire. Dans un déploiement complètement centralisé, tout le trafic du site de succursale est acheminé via des liaisons de réseau étendu. Au lieu de payer pour la bande passante requise pour la liaison de réseau étendu, il est peut-être préférable d’utiliser une jonction SIP distribuée.

> [!NOTE]  
> Pour plus d’informations sur l’utilisation d’un acheminement SIP distribué, reportez-vous à <a href="lync-server-2013-branch-site-sip-trunking.md">Jonction SIP de site de succursale dans Lync Server 2013</a> (contenu éventuellement en anglais) dans la documentation relative à la planification.

## Types de connexion de jonction SIP pris en charge

Lync Server 2013 prend en charge les types de connexion de jonction SIP suivants :

  - Le réseau privé MPLS (Multiprotocol Label Switching) dirige et transporte les données d’un nœud du réseau vers le suivant. La bande passante d’un réseau MPLS est partagée avec d’autres abonnés et un libellé est attribué à chaque paquet de données pour distinguer les données d’un abonné de celles d’un autre. Ce type de connexion ne requiert pas de réseau privé virtuel (VPN). Un des inconvénients possibles est que le trafic IP excessif peut interférer avec le trafic VoIP à moins qu’une priorité soit affectée au trafic VoIP.

  - Une connexion privée sans autre trafic constitue généralement le type de connexion le plus fiable et le plus sûr (par exemple, une connexion en bail à fibre optique ou une ligne T1). Ce type de connexion fournit la capacité de gestion d’appels la plus élevée, mais elle est généralement la plus coûteuse. Un VPN n’est pas nécessaire. Les connexions privées sont adaptées aux entreprises à grands volumes d’appels ou soumises à des exigences strictes en matière de sécurité et de disponibilité.

  - L’Internet public représente le type de connexion le plus économique, mais également le moins fiable et celui qui offre la capacité de gestion des appels la plus faible. Votre fournisseur de services de téléphonie Internet (ITSP) peut sécuriser ce type de connexion par jonction SIP s’il assure une prise en charge des protocoles TLS (Transport Layer Security) et SRTP (Secure Real-Time Transport Protocol) en vue de chiffrer le trafic de signalisation et multimédia. Si vous n’êtes pas en mesure de configurer une connexion par jonction SIP via Internet dans le but d’utiliser TLS et SRTP, nous vous recommandons vivement d’utiliser un tunnel VPN pour bénéficier d’une connexion plus sûre. Contactez votre fournisseur de services de téléphonie Internet pour déterminer s’il offre une prise en charge de TLS avec SRTP.

## Sélection d’un type de connexion

Le type de connexion de jonction SIP le plus approprié à votre entreprise dépend de vos besoins et de votre budget.

  - Pour les entreprises moyennes ou grandes, un réseau MPLS constitue généralement la meilleure solution. Il est capable de fournir la bande passante nécessaire à un tarif moindre qu’un réseau privé spécialisé.

  - Les grandes entreprises peuvent nécessiter une connexion à fibre optique privée ou une connexion T1.

  - Pour une petite entreprise ou un site de succursale avec un faible volume d’appels, l’acheminement SIP via Internet peut être idéal. Ce type de connexion n’est cependant pas recommandé pour les sites de taille moyenne ou grande.

## Prise en charge de codec

Le proxy du fournisseur de services doit prendre en charge les codecs suivants :

  - G.711 a-law (utilisé principalement en dehors de l’Amérique du Nord)

  - G.711 µ-law (utilisé en Amérique du Nord)

