---
title: Prise en charge des jonctions SIP dans Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SIP trunking support
ms:assetid: e3042831-e8d8-4ea2-baa2-1a697401ffa0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399005(v=OCS.15)
ms:contentKeyID: 48185714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2bdcf814a62bed4954c77be76bef32e1b6807ba
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846814"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunking-support-in-lync-server-2013"></a>Prise en charge des jonctions SIP dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-03_

Si vous envisagez d’utiliser Enterprise Voice avec le trunking SIP, vous devez déployer un serveur de médiation et vous assurer que d’autres infrastructures et composants répondent aux exigences de support appropriées à votre modèle de déploiement. Pour plus d’informations sur la façon de déterminer s’il convient d’implémenter le trunking SIP, voir [vue d’ensemble du trunking SIP dans Lync Server 2013](lync-server-2013-overview-of-sip-trunking.md) dans la documentation de planification.

Vous pouvez utiliser le programme Microsoft Unified Communications Open Interoperability pour l’infrastructure de téléphonie pour les entreprises pour rechercher des passerelles de réseau téléphonique commuté (RTC), des PBX IP et des services de trunking SIP qualifiés, y compris la téléphonie IP. prestataires de services. Pour plus d’informations, reportez-vous au site Web Microsoft [http://go.microsoft.com/fwlink/p/?LinkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309)Unified Communications Open Interoperability du programme à l’adresse.

<div>

## <a name="mediation-server-support"></a>Prise en charge du serveur de médiation

Pour implémenter le trunking SIP, vous devez Router la connexion à l’aide d’un serveur de médiation, qui fait office de proxy pour les sessions de communication entre les clients Lync Server 2013 et le fournisseur de service. Le serveur de médiation décode le trafic multimédia de clients et de serveurs, puis le réactive avant de l’envoyer au fournisseur de services. Le encodage est nécessaire, car les Trunks SIP ne prennent pas en charge certains codecs utilisés (par exemple, le protocole RTA) ou la négociation du protocole d’établissement de connexion interactive pour le traversée par un pare-feu.

Chaque serveur de médiation peut avoir deux cartes réseau qui fournissent une interface réseau interne et externe. L’interface externe est généralement appelée interface de passerelle, car elle a traditionnellement servi à se connecter à une passerelle PSTN ou à un PBX IP. Pour implémenter une ligne SIP, vous connectez l’interface externe à un contrôleur de bordure de session (SBC) auprès d’un fournisseur de services.

</div>

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a>Comparatif entre jonction SIP centralisée et jonction SIP distribuée

*Centralisation* Le trunking SIP route tout le trafic VoIP (voix sur IP), y compris le trafic du site de succursales, par le biais du centre de données. Le modèle de déploiement centralisé est simple, rentable et est généralement l’approche préférée pour l’implémentation de Trunks SIP avec Lync Server 2013.

Selon les modèles d’utilisation au sein de votre entreprise, il est possible que vous ne souhaitiez pas acheminer tous les utilisateurs via le Trunk SIP centralisé. Pour vous aider à établir vos besoins, répondez aux questions suivantes :

  - Quelle est la taille de chaque site? Combien d’utilisateurs?

  - Quels sont les numéros de téléphone à composer vers l’intérieur sur chaque site pour obtenir la plupart des appels téléphoniques?

*Distribué* Le trunking SIP est un modèle de déploiement dans lequel vous implémentez un Trunk SIP local au sein d’un ou plusieurs sites de succursale. Le trafic VoIP est alors routé à partir du site de succursale directement vers son prestataire de services, sans passer par le centre de données.

La jonction SIP distribuée n’est requise que dans les cas suivants :

  - Le site de succursale nécessite une connectivité téléphonique plus Survivable (par exemple, si le réseau étendu monte en panne). Si la succursale a besoin d’une redondance et d’un basculement, le prestataire de services facturera davantage et la configuration sera plus longue. Cela doit être analysé pour chaque site de succursale. Certains de vos succursales sont susceptibles de nécessiter une redondance et un basculement, alors que d’autres ne le sont pas.

  - Le site de succursale et le centre de données se trouvent dans des pays/régions différents. Pour des raisons de compatibilité et légales, vous devez disposer d’au moins une jonction SIP par pays/région.

Le choix entre le déploiement d’une trunkation SIP centralisée ou répartie nécessite une analyse coûts-avantages. Dans certains cas, il peut être préférable de choisir le mode de déploiement distribué, même si ce n’est pas nécessaire. Dans un déploiement entièrement centralisé, le trafic de tous les sites de succursales est routé par le biais de liens WAN. Au lieu de payer pour la bande passante requise pour la liaison de réseau étendu, il est peut-être préférable d’utiliser une jonction SIP distribuée.

<div>


> [!NOTE]  
> Pour plus d’informations sur les raisons et la façon dont vous pouvez utiliser le trunking SIP distribué, voir <A href="lync-server-2013-branch-site-sip-trunking.md">trunking SIP site dans Lync Server 2013</A> dans la documentation de planification.



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a>Types de connexion de jonction SIP pris en charge

Lync Server 2013 prend en charge les types de connexion suivants pour le trunking SIP:

  - Le réseau privé MPLS (Multiprotocol Label Switching) dirige et transporte les données d’un nœud du réseau vers le suivant. La bande passante d’un réseau MPLS est partagée avec d’autres abonnés et un libellé est attribué à chaque paquet de données pour distinguer les données d’un abonné de celles d’un autre. Ce type de connexion n’exige pas VPN. Un des inconvénients possibles est que le trafic IP excessif peut interférer avec le trafic VoIP à moins qu’une priorité soit affectée au trafic VoIP.

  - Une connexion privée sans autre trafic est généralement le type de connexion la plus fiable et la plus sécurisée (par exemple, une connexion fibre optique ou une ligne de type T1). Ce type de connexion fournit la plus grande capacité de transport d’appel, mais c’est généralement le plus onéreux. Aucun VPN n’est requis. Les connexions privées conviennent aux organisations dont le volume d’appels est élevé ou dont les exigences de sécurité et de disponibilité sont rigoureuses.

  - L’Internet public est le type de connexion le moins cher, mais également le moins fiable, et celui doté de la plus petite capacité de transport d’appels. Votre fournisseur de services de téléphonie Internet (ITSP) peut vous aider à sécuriser ce type de connexion SIP Trunk s’il prend en charge le protocole TLS (Transport Layer Security) et le protocole SRTP (Secure Real-Time Transport Protocol) pour chiffrer les signaux et le trafic multimédia. Si vous ne parvenez pas à configurer une connexion SIP Trunk via Internet pour utiliser TLS et SRTP, nous vous recommandons vivement d’utiliser un tunnel VPN pour fournir une connexion plus sécurisée. Contactez votre ITSP pour déterminer s’il prend en charge TLS avec SRTP.

<div>

## <a name="selecting-a-connection-type"></a>Sélection d’un type de connexion

Le type de connexion de jonction SIP le plus approprié à votre entreprise dépend de vos besoins et de votre budget.

  - Dans le cas d’une entreprise du milieu ou d’une grande taille, un réseau MPLS fournit généralement le plus de valeur. Il est capable de fournir la bande passante nécessaire à un tarif moindre qu’un réseau privé spécialisé.

  - Les grandes entreprises pourront avoir besoin d’une connexion fibre optique privée ou T1.

  - Dans le cas d’une petite entreprise ou d’un site de succursale avec un volume d’appel faible, le trunking SIP via Internet est le meilleur choix. Toutefois, ce type de connexion n’est pas recommandé pour les sites de taille moyenne ou de grande taille.

</div>

</div>

<div>

## <a name="codec-support"></a>Prise en charge de codec

Le proxy du fournisseur de services doit prendre en charge les codecs suivants:

  - G.711 a-law (utilisé principalement en dehors de l’Amérique du Nord)

  - G.711 µ-law (utilisé en Amérique du Nord)

</div>

</div>

<span> </span>

</div>

</div>

</div>

