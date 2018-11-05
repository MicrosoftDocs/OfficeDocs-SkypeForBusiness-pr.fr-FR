---
title: 'Lync Server 2013 : Implémentation d’une jonction SIP'
TOCTitle: Implémentation d’une une jonction SIP
ms:assetid: 273a22b1-8a4c-4187-acf8-c57d5c6598ce
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425743(v=OCS.15)
ms:contentKeyID: 49296679
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Implémentation d’une jonction SIP dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Pour implémenter la jonction SIP, vous devez acheminer la connexion par l’intermédiaire d’un serveur de médiation, qui joue le rôle d’un proxy pour les sessions de communication entre les clients Lync Server 2013 et le fournisseur de services, et convertit le trafic multimédia lorsque cela est nécessaire.

Chaque serveur de médiation est doté d’une interface réseau interne et externe. L’interface interne se connecte aux serveurs frontaux. L’interface externe est généralement appelée « interface de passerelle », car elle a été traditionnellement utilisée pour connecter le serveur de médiation à une passerelle RTC ou à un système PBX IP. Pour implémenter une jonction SIP, vous connectez l’interface externe du serveur de médiation au composant Edge externe du fournisseur de services de téléphonie Internet.

> [!NOTE]  
> Ce dernier peut être un contrôleur SBC, un routeur ou une passerelle.

Pour plus d’informations sur les serveurs de médiation, reportez-vous à [Composant Serveur de médiation dans Lync Server 2013](lync-server-2013-mediation-server-component.md).

## Comparatif entre jonction SIP centralisée et jonction SIP distribuée

La jonction SIP *centralisée* achemine tout le trafic VoIP, dont le trafic de site de succursale, via votre site central. Le modèle de déploiement centralisé est simple et économique. Il s’agit de l’approche généralement recommandée pour l’implémentation de jonctions SIP avec Lync Server 2013.

La jonction SIP *distribuée* est un modèle de déploiement selon lequel vous mettez en œuvre une jonction SIP locale sur un ou plusieurs sites de succursale. Le trafic VoIP est ensuite acheminé directement du site de succursale vers un fournisseur de services sans passer par le site central.

La jonction SIP distribuée n’est requise que dans les cas suivants :

  - Le site de succursale requiert une connectivité téléphonique de secours (par exemple, en cas de panne du réseau étendu \[WAN\]). Ce besoin doit être évalué pour chaque site de succursale : la redondance et le basculement peuvent être nécessaires à certaines succursales et non à d’autres.

  - Une résistance est requise entre deux sites centraux. Vous devez vous assurer qu’une terminaison de jonction SIP est présente sur chaque site central. Prenons le cas par exemple, de deux sites centraux (Dublin et Tukwila) qui utilisent la jonction SIP de l’un des sites. En cas de défaillance de la jonction, les utilisateurs de l’autre site ne peuvent pas passer d’appels RTC.

  - Le site de succursale et le site central se situent dans des pays/régions différents. Pour des raisons de compatibilité et légales, vous devez disposer d’au moins une jonction SIP par pays/région. Par exemple, dans l’Union Européenne, les communications ne peuvent pas sortir d’un pays ou d’une région sans terminaison locale à un point centralisé.

Selon l’emplacement géographique des sites et le trafic anticipé au sein de votre entreprise, il peut être judicieux de ne pas acheminer l’ensemble des utilisateurs vers une jonction SIP centrale ou d’acheminer certains utilisateurs vers une jonction SIP située sur le site de leur site de succursale. Pour vous aider à établir vos besoins, répondez aux questions suivantes :

  - Quelle est la taille de chaque site (autrement dit, combien d’utilisateurs sont activés pour Voix Entreprise) ?

  - Quels numéros de Sélection directe à l’arrivée (SDA) reçoivent le plus grand nombre d’appels sur chaque site ?

La décision d’opter pour une jonction SIP centralisée ou distribuée doit être basée sur une analyse des coûts-avantages. Dans certains cas, il peut être plus avantageux d’opter pour un modèle de déploiement distribué, même s’il n’est pas nécessaire. Dans un environnement entièrement centralisé, tout le trafic de site de succursale est acheminé via des liaisons de réseau étendu (WAN). Au lieu de payer pour la bande passante requise pour la liaison de réseau étendu, il est peut-être préférable d’utiliser une jonction SIP distribuée. Par exemple, vous pouvez déployer un serveur Standard Edition sur un site de succursale fédéré au site central ou déployer un Survivable Branch Appliance ou un serveur Survivable Branch Server avec une petite passerelle.

> [!NOTE]  
> Pour plus d’informations sur la jonction SIP distribuée, reportez-vous à <a href="lync-server-2013-branch-site-sip-trunking.md">Jonction SIP de site de succursale dans Lync Server 2013</a>.

## Types de connexion de jonction SIP pris en charge

Lync Server prend en charge les types de connexion de jonction SIP suivants :

  - Le réseau privé MPLS (Multiprotocol Label Switching) dirige et transporte les données d’un nœud du réseau vers le suivant. La bande passante d’un réseau MPLS est partagée avec d’autres abonnés et un libellé est attribué à chaque paquet de données pour distinguer les données d’un abonné de celles d’un autre. Ce type de connexion ne requiert pas de réseau privé virtuel (VPN). Un des inconvénients possibles est que le trafic IP excessif peut interférer avec le trafic VoIP à moins qu’une priorité soit affectée au trafic VoIP.

  - Une connexion privée sans autre trafic, par exemple, une connexion à fibre optique louée ou une ligne T1, est généralement le type de connexion le plus fiable et le plus sûr. En effet, elle offre la capacité la plus élevée en matière de transport des appels. Cependant, elle est généralement plus chère. Un VPN n’est pas nécessaire. Les connexions privées sont adaptées aux organisations à grands volumes d’appels ou soumises à des exigences strictes en matière de sécurité et de disponibilité.

  - Internet est le type de connexion le moins cher, mais aussi le moins fiable. La connexion Internet est le seul type de connexion par jonction SIP Lync Server qui requiert un VPN.

## Sélection d’un type de connexion

Le type de connexion de jonction SIP le plus approprié à votre entreprise dépend de vos besoins et de votre budget.

  - Pour les grandes et moyennes entreprises, un réseau MPLS offre en général la meilleure valeur. Il est capable de fournir la bande passante nécessaire à un tarif moindre qu’un réseau privé spécialisé.

  - Pour les grandes entreprises, une connexion privée à fibre optique, T1, T3 ou supérieure (E1, E3 ou supérieure dans l’Union Européenne) peut être adaptée.

  - Pour les petites entreprises ou les site de succursale à faibles volumes d’appels, une jonction SIP via Internet peut être la meilleure option. Ce type de connexion n’est pas recommandé pour les sites de taille moyenne ou de grande taille.

## Bande passante requise

La capacité d’appels (c’est-à-dire le nombre d’appels simultanés devant être pris en charge) détermine la bande passante requise pour votre implémentation. Vous devez prendre en compte la disponibilité de la bande passante pour pouvoir tirer parti de la capacité maximale facturée. Calculez vos besoins en bande passante de jonction SIP maximale à l’aide de la formule suivante :

Bande passante de jonction SIP maximale = Nbre max. d’appels simultanés (64 Kbits/s + taille d’en-tête)

> [!NOTE]  
> La taille d’en-tête maximale est de 20 octets.

## Prise en charge de codec

Lync Server 2013 prend en charge uniquement les codecs suivants :

  - G.711 a-law (utilisé principalement en dehors de l’Amérique du Nord)

  - G.711 µ-law (utilisé en Amérique du Nord)

## Fournisseur de services de téléphonie Internet

La manière dont vous mettez en œuvre le côté fournisseur de services d’une connexion de jonction SIP varie d’un fournisseur de services de téléphonie Internet à l’autre. Pour plus d’informations sur le déploiement, contactez votre fournisseur de services. Pour obtenir une liste des fournisseurs de services de jonction SIP approuvés, reportez-vous au [site web du programme ouvert d’interopérabilité des communications unifiées Microsoft](http://go.microsoft.com/fwlink/?linkid=287029).

Pour plus d’informations sur les fournisseurs de jonctions SIP approuvés par Microsoft, contactez votre représentant Microsoft.

> [!IMPORTANT]  
> Vous devez utiliser un fournisseur de services approuvé par Microsoft pour garantir que votre fournisseur de services de téléphonie Internet prend en charge toutes les fonctionnalités qui transitent par la jonction SIP (par exemple, la configuration et la gestion des sessions et la prise en charge des services VoIP étendus). Le support technique Microsoft ne s’étend pas aux configurations qui utilisent des fournisseurs non approuvés. Si vous utilisez actuellement un fournisseur de services Internet non approuvé pour la jonction SIP, vous pouvez envisager de continuer à utiliser ce fournisseur en tant que FAI et utiliser un fournisseur approuvé par Microsoft pour la jonction SIP.
