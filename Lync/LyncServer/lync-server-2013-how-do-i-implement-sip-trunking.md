---
title: 'Lync Server 2013 : Implémentation d’une jonction SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: How do I implement SIP trunking?
ms:assetid: 273a22b1-8a4c-4187-acf8-c57d5c6598ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425743(v=OCS.15)
ms:contentKeyID: 48183666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de621d7508b69dd3adc3babf487406825f3a93f1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738944"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-do-i-implement-sip-trunking-in-lync-server-2013"></a>Implémentation d’une jonction SIP dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-18_

Pour implémenter le trunking SIP, vous devez Router la connexion à l’aide d’un serveur de médiation, qui fait office de proxy pour les sessions de communication entre les clients Lync Server 2013 et le fournisseur de service, et transcode le média, si nécessaire.

Chaque serveur de médiation possède une interface réseau interne et une interface réseau externe. L’interface interne se connecte aux serveurs frontaux. L’interface externe est généralement appelée interface de la passerelle, car elle a traditionnellement été utilisée pour connecter le serveur de médiation à une passerelle de réseau téléphonique commuté (PSTN) ou un PBX IP. Pour implémenter une ligne SIP, vous connectez l’interface externe du serveur de médiation au composant de bord externe du ITSP.

<div>


> [!NOTE]  
> Ce dernier peut être un contrôleur de session en périphérie (SBC), un routeur ou une passerelle.



</div>

Pour plus d’informations sur les serveurs de médiation, voir [composant serveur de médiation dans Lync Server 2013](lync-server-2013-mediation-server-component.md).

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a>Comparatif entre jonction SIP centralisée et jonction SIP distribuée

*Centralisation* Le trunking SIP achemine tout le trafic VoIP (voix sur IP), y compris le trafic du site de succursale, par le biais de votre site central. Le modèle de déploiement centralisé est simple, rentable et est généralement l’approche recommandée pour l’implémentation de Trunks SIP avec Lync Server 2013.

*Distribué* Le trunking SIP est un modèle de déploiement dans lequel vous implémentez un Trunk SIP local au sein d’un ou plusieurs sites de succursale. Le trafic VoIP est alors acheminé à partir du site de succursale directement vers un fournisseur de services, sans passer par le site central.

La jonction SIP distribuée n’est requise que dans les cas suivants :

  - Le site de succursale nécessite une connectivité téléphonique plus Survivable (par exemple, si le réseau étendu monte en panne). Cette obligation doit être analysée pour chaque site de succursale ; Il est possible que certaines de vos succursales nécessitent une redondance et un basculement, alors que d’autres ne le sont pas.

  - La résilience est requise entre deux sites centraux. Vous devez vous assurer qu’un Trunk SIP s’arrête sur chaque site central. Par exemple, si vous avez des sites centraux de Dublin et Tukwila et que vous utilisez uniquement le Trunk SIP d’un site, si le Trunk s’arrête, les utilisateurs du site ne peuvent pas passer d’appels RTC.

  - Le site de succursale et le site central sont dans des pays/régions différents. Pour des raisons de compatibilité et légales, vous devez disposer d’au moins une jonction SIP par pays/région. Par exemple, dans l’Union Européenne, les communications ne peuvent pas sortir d’un pays ou d’une région sans terminaison locale à un point centralisé.

En fonction de l’emplacement géographique des sites et de la quantité de trafic que vous prévoyez au sein de votre entreprise, il est possible que vous ne souhaitiez pas acheminer tous les utilisateurs par le biais du réseau SIP central ou vous pouvez choisir de router des utilisateurs via une ligne SIP sur leur site de succursale. Pour vous aider à établir vos besoins, répondez aux questions suivantes :

  - Quel est le niveau de chaque site (c’est-à-dire le nombre d’utilisateurs activés pour Enterprise Voice) ?

  - Quels numéros de Sélection directe à l’arrivée (SDA) reçoivent le plus grand nombre d’appels sur chaque site ?

La décision d’opter pour une jonction SIP centralisée ou distribuée doit être basée sur une analyse des coûts-avantages. Dans certains cas, il peut être plus avantageux d’opter pour un modèle de déploiement distribué, même s’il n’est pas nécessaire. Dans un déploiement entièrement centralisé, le trafic de tous les sites de succursales est routé par le biais de liens WAN. Au lieu de payer pour la bande passante requise pour la liaison de réseau étendu, il est peut-être préférable d’utiliser une jonction SIP distribuée. Par exemple, vous pouvez choisir de déployer un serveur Standard Edition sur un site de succursale avec la Fédération sur le site central, ou vous pouvez déployer une application de succursale Survivable ou un serveur de succursales survivant avec une petite passerelle.

<div>


> [!NOTE]  
> Pour plus d’informations sur le trunking SIP distribué, voir <A href="lync-server-2013-branch-site-sip-trunking.md">trunking SIP site dans Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a>Types de connexion de jonction SIP pris en charge

Lync Server prend en charge les types de connexion suivants pour le trunking SIP :

  - Le réseau privé MPLS (Multiprotocol Label Switching) dirige et transporte les données d’un nœud du réseau vers le suivant. La bande passante d’un réseau MPLS est partagée avec d’autres abonnés et un libellé est attribué à chaque paquet de données pour distinguer les données d’un abonné de celles d’un autre. Ce type de connexion ne requiert pas de réseau privé virtuel (VPN). Un des inconvénients possibles est que le trafic IP excessif peut interférer avec le trafic VoIP à moins qu’une priorité soit affectée au trafic VoIP.

  - Une connexion privée sans autre trafic, par exemple, une connexion à fibre optique louée ou une ligne T1, est généralement le type de connexion le plus fiable et le plus sûr. En effet, elle offre la capacité la plus élevée en matière de transport des appels. Cependant, elle est généralement plus chère. Un VPN n’est pas nécessaire. Les connexions privées sont adaptées aux organisations à grands volumes d’appels ou soumises à des exigences strictes en matière de sécurité et de disponibilité.

  - Internet est le type de connexion le moins cher, mais aussi le moins fiable. Connexion Internet est le seul type de connexion de trunking SIP de Lync Server qui nécessite un réseau privé virtuel (VPN).

<div>

## <a name="selecting-a-connection-type"></a>Sélection d’un type de connexion

Le type de connexion de jonction SIP le plus approprié à votre entreprise dépend de vos besoins et de votre budget.

  - Pour les grandes et moyennes entreprises, un réseau MPLS offre en général la meilleure valeur. Il est capable de fournir la bande passante nécessaire à un tarif moindre qu’un réseau privé spécialisé.

  - Pour les grandes entreprises, une connexion privée à fibre optique, T1, T3 ou supérieure (E1, E3 ou supérieure dans l’Union Européenne) peut être adaptée.

  - Dans le cas d’une petite entreprise ou d’un site de succursale avec un volume d’appel faible, le trunking SIP via Internet est le meilleur choix. Ce type de connexion n’est pas recommandé pour les sites de taille moyenne ou de grande taille.

</div>

</div>

<div>

## <a name="bandwidth-requirements"></a>Bande passante requise

La capacité d’appels (c’est-à-dire le nombre d’appels simultanés devant être pris en charge) détermine la bande passante requise pour votre implémentation. Vous devez prendre en compte la disponibilité de la bande passante pour pouvoir tirer parti de la capacité maximale facturée. Calculez vos besoins en bande passante de jonction SIP maximale à l’aide de la formule suivante :

Bande passante de jonction SIP maximale = Nbre max. d’appels simultanés (64 Kbits/s + taille d’en-tête)

<div>


> [!NOTE]  
> La taille d’en-tête maximale est de 20 octets.



</div>

</div>

<div>

## <a name="codec-support"></a>Prise en charge de codec

Lync Server 2013 ne prend en charge que les codecs suivants :

  - G.711 a-law (utilisé principalement en dehors de l’Amérique du Nord)

  - G.711 µ-law (utilisé en Amérique du Nord)

</div>

<div>

## <a name="internet-telephony-service-provider"></a>Fournisseur de services de téléphonie Internet

La manière dont vous mettez en œuvre le côté fournisseur de services d’une connexion de jonction SIP varie d’un fournisseur de services de téléphonie Internet à l’autre. Pour plus d’informations sur le déploiement, contactez votre fournisseur de services. Pour obtenir la liste des fournisseurs de services de trunking SIP certifiés, voir [site Web du programme d’interopérabilité Microsoft Unified Communications](http://go.microsoft.com/fwlink/?linkid=287029).

Pour plus d’informations sur les fournisseurs de jonctions SIP approuvés par Microsoft, contactez votre représentant Microsoft.

<div>


> [!IMPORTANT]  
> Vous devez utiliser un fournisseur de services approuvé par Microsoft pour garantir que votre fournisseur de services de téléphonie Internet prend en charge toutes les fonctionnalités qui transitent par la jonction SIP (par exemple, la configuration et la gestion des sessions et la prise en charge des services VoIP étendus). Le support technique Microsoft ne s’étend pas aux configurations qui utilisent des fournisseurs non approuvés. Si vous utilisez actuellement un fournisseur de services Internet non approuvé pour la jonction SIP, vous pouvez envisager de continuer à utiliser ce fournisseur en tant que FAI et utiliser un fournisseur approuvé par Microsoft pour la jonction SIP.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

