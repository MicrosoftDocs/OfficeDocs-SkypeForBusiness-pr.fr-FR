---
title: 'Lync Server 2013 : vue d’ensemble de contournement de média'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of media bypass
ms:assetid: 9ea090b3-f607-46f7-97dd-2510052524e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412740(v=OCS.15)
ms:contentKeyID: 48184924
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84c70cae521deebecf30e7c8ec6505b18e9842fa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755498"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-media-bypass-in-lync-server-2013"></a>Présentation de l’exclusion de médias dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-21_

La dérivation de média est utile lorsque vous voulez réduire le nombre de serveurs de médiation déployés. En règle générale, un pool de serveurs de médiation est déployé sur un site central et contrôle les passerelles dans les sites de succursales. L’activation de la déviation du trafic multimédia permet aux médias de passer des appels PSTN (réseau téléphonique commuté) depuis des clients situés sur les sites de succursale directement par les passerelles de ces sites. Les itinéraires d’appels sortants de Lync Server 2013 et les stratégies voix entreprise doivent être correctement configurés pour que les appels RTC de clients sur un site de succursale soient routés vers la passerelle appropriée.

Les réseaux Wi-Fi subissent généralement plus de pertes de paquets que les réseaux câblés. La récupération de cette perte de paquets n’est habituellement pas très bien supportée par les passerelles. C’est pourquoi nous vous conseillons d’évaluer la qualité d’un réseau Wi-Fi avant de déterminer si le contournement doit être activé pour un sous-réseau sans fil. Il convient également de tenir compte d’un compromis entre diminution de la latence et récupération de perte de paquets. RTAudio, un codec disponible pour les appels qui ne contournent pas le serveur de médiation, convient davantage à la gestion de la perte de paquets.

Une fois que votre structure vocale d’entreprise est en place, il est facile de planifier une dérivation multimédia.

  - Si vous avez une topologie centralisée sans liaison de réseau distant vers les sites de succursale, vous pouvez activer la déviation du trafic multimédia car il n’est pas nécessaire d’affiner le contrôle.

  - Si votre topologie distribuée est constituée d’une ou plusieurs régions réseau et de leurs sites de succursale affiliés, déterminez les éléments suivants :
    
      - Si vos homologues de serveur de médiation sont en mesure de prendre en charge les fonctionnalités requises pour la déviation du trafic multimédia.
    
      - Quels sont les sites bien connectés dans chaque région réseau.
    
      - Quelle combinaison de déviation du trafic multimédia et de contrôle d’admission des appels est appropriée pour votre réseau.

Lorsque vous activez la déviation du trafic multimédia, un ID unique de contournement est généré automatiquement pour une région réseau et pour tous les sites réseau sans restrictions de bande passante au sein de cette région. Les sites avec restrictions de bande passante dans la région et les sites connectés à la région sur les liaisons du réseau étendu se voient attribués à chacun un ID de contournement unique.

Lorsqu’un utilisateur effectue un appel vers le RTC, le serveur de médiation compare l’ID de contournement du sous-réseau du client à l’ID de contournement du sous-réseau de la passerelle. Si les deux ID de contournement concordent, la déviation du trafic multimédia est utilisée pour l’appel. Si les ID de contournement ne correspondent pas, le média de l’appel doit être acheminé via le serveur de médiation.

Lorsqu’un utilisateur reçoit un appel depuis le réseau téléphonique commuté, le client de l’utilisateur compare son ID de contournement à celui de la passerelle PSTN. Si les deux ID de contournement correspondent, les flux multimédias sont directement de la passerelle au client, en ignorant le serveur de médiation.

Seuls Lync 2010 ou les clients et appareils supérieurs prennent en charge les interactions de contournement multimédia avec un serveur de médiation.

<div>


> [!IMPORTANT]  
> En plus d’autoriser la déviation du trafic multimédia global, vous devez autoriser la déviation du trafic multimédia individuellement sur chaque jonction PSTN. Si le contournement est autorisé globalement mais ne l’est pas pour une jonction PSTN donnée, la déviation du trafic multimédia ne sera appelée pour aucun appel impliquant cette jonction PSTN. En outre, lorsque la déviation du trafic multimédia est définie sur <STRONG>Utiliser les informations de site et de région</STRONG>, vous devez associer tous les sous-réseaux routables aux sites sur lesquels ils se situent. Si un site compte des sous-réseaux routables pour lesquels le contournement n’est pas souhaité, ces sous-réseaux devront être regroupés dans un nouveau site avant d’autoriser la déviation du trafic multimédia. Vous êtes ainsi assuré que les sous-réseaux non routables recevront un ID de contournement distinct.



</div>

<div>

## <a name="see-also"></a>Voir aussi


[Modes de déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-media-bypass-modes.md)  
[Déviation du trafic multimédia et contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-media-bypass-and-call-admission-control.md)  
[Configuration technique requise pour la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

