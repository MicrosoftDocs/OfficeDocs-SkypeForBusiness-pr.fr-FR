---
title: 'Lync Server 2013 : comment implémenter la jonction SIP ?'
description: 'Lync Server 2013 : comment implémenter la jonction SIP ?.'
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
ms.openlocfilehash: 10882adc0bff573868dcd07268ed0446385d895c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553150"
---
# <a name="how-do-i-implement-sip-trunking-in-lync-server-2013"></a>Comment implémenter la jonction SIP dans Lync Server 2013 ?

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-18_

Pour implémenter la jonction SIP, vous devez acheminer la connexion via un serveur de médiation qui agit comme un proxy pour les sessions de communication entre les clients Lync Server 2013 et le fournisseur de services et transcode les médias, si nécessaire.

Chaque serveur de médiation possède une interface réseau interne et une interface réseau externe. L’interface interne se connecte aux serveurs frontaux. L’interface externe est communément appelée interface de passerelle car elle a traditionnellement été utilisée pour connecter le serveur de médiation à une passerelle RTC (réseau téléphonique commuté) ou à un IP-PBX. Pour implémenter une jonction SIP, vous connectez l’interface externe du serveur de médiation au composant Edge externe du téléphonie Internet.

<div>


> [!NOTE]  
> Ce dernier peut être un contrôleur SBC, un routeur ou une passerelle.



</div>

Pour plus d’informations sur les serveurs de médiation, reportez-vous à la rubrique [Mediation Server Component in Lync server 2013](lync-server-2013-mediation-server-component.md).

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a>Comparatif entre jonction SIP centralisée et jonction SIP distribuée

*Centralisé* La jonction SIP achemine tout le trafic VoIP (Voice over Internet Protocol), y compris le trafic de site de succursale, via votre site central. Le modèle de déploiement centralisé est simple, rentable et constitue généralement l’approche recommandée pour l’implémentation de jonctions SIP avec Lync Server 2013.

*Distribué* La jonction SIP est un modèle de déploiement dans lequel vous implémentez une jonction SIP locale sur un ou plusieurs sites de succursale. Le trafic VoIP est ensuite acheminé à partir du site de succursale directement vers un fournisseur de services sans passer par le site central.

La jonction SIP distribuée n’est requise que dans les cas suivants :

  - Le site de succursale nécessite une connectivité téléphonique de secours (par exemple, en cas de panne de la liaison WAN). Cette exigence doit être analysée pour chaque site de succursale ; certaines de vos succursales peuvent nécessiter une redondance et un basculement, tandis que d’autres ne le sont pas.

  - La résilience est requise entre deux sites centraux. Vous devez vous assurer qu’une jonction SIP s’arrête sur chaque site central. Par exemple, si vous disposez de sites centraux Dublin et Tukwila et que tous deux utilisent uniquement la jonction SIP d’un site, si la jonction tombe en panne, les utilisateurs de l’autre site ne peuvent pas passer des appels PSTN.

  - Le site de succursale et le site central se situent dans des pays/régions différents. Pour des raisons de compatibilité et légales, vous devez disposer d’au moins une jonction SIP par pays/région. Par exemple, dans l’Union Européenne, les communications ne peuvent pas sortir d’un pays ou d’une région sans terminaison locale à un point centralisé.

En fonction de l’emplacement géographique des sites et de la somme du trafic que vous prévoyez au sein de votre entreprise, vous pouvez ne pas vouloir acheminer tous les utilisateurs via la jonction SIP centrale ou vous pouvez choisir d’acheminer certains utilisateurs via une jonction SIP sur leur site de succursale. Pour vous aider à établir vos besoins, répondez aux questions suivantes :

  - Quelle est la taille de chaque site (autrement dit, combien d’utilisateurs sont activés pour voix entreprise) ?

  - Quels numéros de Sélection directe à l’arrivée (SDA) reçoivent le plus grand nombre d’appels sur chaque site ?

La décision d’opter pour une jonction SIP centralisée ou distribuée doit être basée sur une analyse des coûts-avantages. Dans certains cas, il peut être plus avantageux d’opter pour un modèle de déploiement distribué, même s’il n’est pas nécessaire. Dans un déploiement complètement centralisé, tout le trafic du site de succursale est acheminé via des liaisons WAN. Au lieu de payer pour la bande passante requise pour la liaison WAN, il est peut-être préférable d’utiliser une jonction SIP distribuée. Par exemple, vous souhaiterez peut-être déployer un serveur Standard Edition sur un site de succursale avec la Fédération sur le site central, ou vous pouvez déployer un Survivable Branch Appliance ou un serveur Survivable Branch Server avec une petite passerelle.

<div>


> [!NOTE]  
> Pour plus d’informations sur la jonction SIP distribuée, voir <A href="lync-server-2013-branch-site-sip-trunking.md">Branch site SIP Trunking in Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a>Types de connexion de jonction SIP pris en charge

Lync Server prend en charge les types de connexion suivants pour la jonction SIP :

  - Le réseau privé MPLS (Multiprotocol Label Switching) dirige et transporte les données d’un nœud du réseau vers le suivant. La bande passante d’un réseau MPLS est partagée avec d’autres abonnés et un libellé est attribué à chaque paquet de données pour distinguer les données d’un abonné de celles d’un autre. Ce type de connexion ne requiert pas de réseau privé virtuel (VPN). Un des inconvénients possibles est que le trafic IP excessif peut interférer avec le trafic VoIP à moins qu’une priorité ne soit affectée au trafic VoIP.

  - Une connexion privée sans autre trafic, par exemple une connexion à fibre optique louée ou une ligne T1, est généralement le type de connexion le plus fiable et le plus sûr. En effet, elle offre la capacité la plus élevée en matière de transport des appels. Toutefois, elle est généralement plus chère. Un VPN n’est pas nécessaire. Les connexions privées sont adaptées aux organisations à grands volumes d’appels ou soumises à des exigences strictes en matière de sécurité et de disponibilité.

  - Internet est le type de connexion le moins cher, mais aussi le moins fiable. La connexion Internet est le seul type de connexion de jonction SIP de Lync Server qui requiert le VPN.

<div>

## <a name="selecting-a-connection-type"></a>Sélection d’un type de connexion

Le type de connexion de jonction SIP le plus approprié à votre entreprise dépend de vos besoins et de votre budget.

  - Pour les grandes et moyennes entreprises, un réseau MPLS offre en général la meilleure valeur. Il est capable de fournir la bande passante nécessaire à un tarif moindre qu’un réseau privé spécialisé.

  - Pour les grandes entreprises, une connexion privée à fibre optique, T1, T3 ou supérieure (E1, E3 ou supérieure dans l’Union Européenne) peut être adaptée.

  - Pour une petite entreprise ou un site de succursale avec un faible volume d’appels, la jonction SIP via Internet peut être le meilleur choix. Ce type de connexion n’est pas recommandé pour les sites de taille moyenne ou de grande taille.

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

Lync Server 2013 prend en charge uniquement les codecs suivants :

  - G.711 a-law (utilisé principalement en dehors de l’Amérique du Nord)

  - G.711 µ-law (utilisé en Amérique du Nord)

</div>

<div>

## <a name="internet-telephony-service-provider"></a>Fournisseur de services de téléphonie Internet

La manière dont vous mettez en œuvre le côté fournisseur de services d’une connexion de jonction SIP varie d’un fournisseur de services de téléphonie Internet à l’autre. Pour plus d’informations sur le déploiement, contactez votre fournisseur de services. Pour obtenir la liste des fournisseurs de services de jonction SIP certifiés, consultez le [site Web Microsoft Unified Communications Open Interoperability Program](https://go.microsoft.com/fwlink/?linkid=287029).

Pour plus d’informations sur les fournisseurs de jonctions SIP approuvés par Microsoft, contactez votre représentant Microsoft.

<div>


> [!IMPORTANT]  
> Vous devez utiliser un fournisseur de services approuvé par Microsoft pour garantir que votre fournisseur de services de téléphonie Internet prend en charge toutes les fonctionnalités qui transitent par la jonction SIP (par exemple la configuration et la gestion des sessions, et la prise en charge des services VoIP étendus). Le support technique Microsoft ne s’étend pas aux configurations qui utilisent des fournisseurs non approuvés. Si vous utilisez actuellement un fournisseur de services Internet non approuvé pour la jonction SIP, vous pouvez envisager de continuer à utiliser ce fournisseur en tant que FAI et utiliser un fournisseur approuvé par Microsoft pour la jonction SIP.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

