---
title: Prise en charge de la jonction SIP de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunking support
ms:assetid: e3042831-e8d8-4ea2-baa2-1a697401ffa0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399005(v=OCS.15)
ms:contentKeyID: 48185714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f31159a2d14facbdfed2f74f3567081699a7bde9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181837"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sip-trunking-support-in-lync-server-2013"></a>Prise en charge de la jonction SIP dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-03_

Si vous envisagez d’utiliser la voix entreprise avec la jonction SIP, vous devez déployer un serveur de médiation et vous assurer que d’autres infrastructures et composants répondent aux exigences de prise en charge appropriées à votre modèle de déploiement. Pour plus d’informations sur la façon de déterminer s’il faut implémenter la jonction SIP, voir [Overview of SIP Trunking in Lync Server 2013](lync-server-2013-overview-of-sip-trunking.md) dans la documentation de planification.

Vous pouvez utiliser le programme d’interopérabilité Open Communications Microsoft pour l’infrastructure de téléphonie d’entreprise pour rechercher les passerelles RTC (réseau téléphonique commuté), les PBX IP et les services de jonction SIP qualifiés, y compris la téléphonie IP qualifiée fournisseurs de services. Pour plus d’informations, consultez le site Web Microsoft Unified Communications Open [https://go.microsoft.com/fwlink/p/?LinkId=203309](https://go.microsoft.com/fwlink/p/?linkid=203309)Interoperability Program à l’adresse.

<div>

## <a name="mediation-server-support"></a>Prise en charge du serveur de médiation

Pour implémenter la jonction SIP, vous devez acheminer la connexion via un serveur de médiation qui agit comme un proxy pour les sessions de communication entre les clients Lync Server 2013 et le fournisseur de services. Le serveur de médiation décode le trafic multimédia provenant des clients et serveurs puis le réencode avant de l’envoyer au fournisseur de services. Le ré-encodage est nécessaire, car les jonctions SIP ne prennent pas en charge certains codecs utilisés, comme la négociation RTA (Real Time audio) ou la négociation de protocole d’établissement de connectivité interactive pour le traversée du pare-feu.

Chaque serveur de médiation peut comporter deux cartes réseau, fournissant une interface réseau interne et externe. L’interface externe est communément appelée interface de passerelle car elle a généralement été utilisée pour se connecter à une passerelle RTC ou à un PBX IP. Pour mettre en œuvre un acheminement SIP, vous connectez l’interface externe à un contrôleur de session en périphérie (SBC) au niveau d’un fournisseur de services.

</div>

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a>Comparatif entre jonction SIP centralisée et jonction SIP distribuée

*Centralisé* La jonction SIP achemine tout le trafic VoIP (Voice over Internet Protocol), y compris le trafic de site de succursale, via votre centre de données. Le modèle de déploiement centralisé est simple, rentable et constitue généralement l’approche par défaut pour l’implémentation de jonctions SIP avec Lync Server 2013.

Selon les modèles d’utilisation de votre entreprise, vous pouvez choisir de ne pas acheminer tous les utilisateurs via un acheminement SIP centralisé. Pour vous aider à établir vos besoins, répondez aux questions suivantes :

  - Quelle est la taille de chaque site ? Combien y a-t-il d’utilisateurs ?

  - Quels numéros de Sélection directe à l’arrivée (SDA) reçoivent le plus grand nombre d’appels sur chaque site ?

La jonction SIP *distribuée* est un modèle de déploiement selon lequel vous mettez en œuvre une jonction SIP locale sur un ou plusieurs sites de succursale. Le trafic VoIP est ensuite acheminé à partir du site de succursale directement à son fournisseur de services, sans passer par votre centre de données.

La jonction SIP distribuée n’est requise que dans les cas suivants :

  - Le site de succursale nécessite une connectivité téléphonique de secours (par exemple, en cas de panne de la liaison WAN). Si la succursale n’a pas besoin d’une fonctionnalité de redondance et de basculement, le fournisseur de services facturera davantage et la configuration sera plus longue. Cette éventualité devrait être étudiée pour chaque site de succursale. Certaines de vos succursales peuvent nécessiter une redondance et un basculement, tandis que d’autres ne le sont pas.

  - Le site de succursale et le centre de données sont situés dans différents pays/régions. Pour des raisons de compatibilité et légales, vous devez disposer d’au moins une jonction SIP par pays/région.

La décision de déployer une jonction SIP centralisée ou distribuée nécessite une analyse coûts-avantages. Dans certains cas, il peut être avantageux d’opter pour le mode de déploiement distribué, même si cela n’est pas obligatoire. Dans un déploiement complètement centralisé, tout le trafic du site de succursale est acheminé via des liaisons WAN. Au lieu de payer pour la bande passante requise pour la liaison WAN, il est peut-être préférable d’utiliser une jonction SIP distribuée.

<div>


> [!NOTE]  
> Pour plus d’informations sur la façon dont vous pouvez utiliser la jonction SIP distribuée, voir <A href="lync-server-2013-branch-site-sip-trunking.md">Branch site SIP Trunking in Lync Server 2013</A> dans la documentation de planification.



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a>Types de connexion de jonction SIP pris en charge

Lync Server 2013 prend en charge les types de connexion suivants pour la jonction SIP :

  - Le réseau privé MPLS (Multiprotocol Label Switching) dirige et transporte les données d’un nœud du réseau vers le suivant. La bande passante d’un réseau MPLS est partagée avec d’autres abonnés et un libellé est attribué à chaque paquet de données pour distinguer les données d’un abonné de celles d’un autre. Ce type de connexion ne requiert pas de réseau privé virtuel (VPN). Un des inconvénients possibles est que le trafic IP excessif peut interférer avec le trafic VoIP à moins qu’une priorité soit affectée au trafic VoIP.

  - Une connexion privée sans autre trafic constitue généralement le type de connexion le plus fiable et le plus sûr (par exemple, une connexion en bail à fibre optique ou une ligne T1). Ce type de connexion fournit la capacité de gestion d’appels la plus élevée, mais elle est généralement la plus coûteuse. Un VPN n’est pas nécessaire. Les connexions privées sont adaptées aux organisations à grands volumes d’appels ou soumises à des exigences strictes en matière de sécurité et de disponibilité.

  - L’Internet public représente le type de connexion le plus économique, mais également le moins fiable et celui qui offre la capacité de gestion des appels la plus faible. Votre fournisseur de services de téléphonie Internet (téléphonie Internet) peut vous aider à sécuriser ce type de connexion de jonction SIP s’il prend en charge le protocole TLS (Transport Layer Security) et SRTP (Secure Real-Time Transport Protocol) pour chiffrer le trafic de signalisation et le trafic multimédia. Si vous n’êtes pas en mesure de configurer une connexion par jonction SIP via Internet dans le but d’utiliser TLS et SRTP, nous vous recommandons vivement d’utiliser un tunnel VPN pour bénéficier d’une connexion plus sûre. Contactez votre fournisseur de services de téléphonie Internet pour déterminer s’il offre une prise en charge de TLS avec SRTP.

<div>

## <a name="selecting-a-connection-type"></a>Sélection d’un type de connexion

Le type de connexion de jonction SIP le plus approprié à votre entreprise dépend de vos besoins et de votre budget.

  - Pour une entreprise de taille moyenne ou grande, un réseau MPLS fournit généralement le plus de valeur. Il est capable de fournir la bande passante nécessaire à un tarif moindre qu’un réseau privé spécialisé.

  - Les grandes entreprises peuvent nécessiter une connexion à fibre optique privée ou une connexion T1.

  - Pour une petite entreprise ou un site de succursale avec un faible volume d’appels, la jonction SIP via Internet peut être le meilleur choix. Toutefois, ce type de connexion n’est pas recommandé pour les sites de taille moyenne ou grande.

</div>

</div>

<div>

## <a name="codec-support"></a>Prise en charge de codec

Le proxy du fournisseur de services doit prendre en charge les codecs suivants :

  - G.711 a-law (utilisé principalement en dehors de l’Amérique du Nord)

  - G.711 µ-law (utilisé en Amérique du Nord)

</div>

</div>

<span> </span>

</div>

</div>

</div>

