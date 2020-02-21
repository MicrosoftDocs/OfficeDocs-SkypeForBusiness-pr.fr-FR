---
title: 'Lync Server 2013 : vue d’ensemble de la déviation du trafic multimédia'
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
ms.openlocfilehash: 66c2484b656cce15a6f7d013060c1fc95047f49d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215950"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-media-bypass-in-lync-server-2013"></a>Vue d’ensemble de la déviation du trafic multimédia dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-21_

Le contournement de média est utile lorsque vous voulez réduire le nombre de serveurs de médiation déployés. Un pool de serveurs de médiation est généralement déployé sur un site central et contrôle des passerelles sur des sites de succursale. L’activation du contournement de média permet aux médias de passer des appels PSTN (Public Switched Telephone Network) depuis des clients situés sur les sites de succursale directement par les passerelles de ces sites. Les itinéraires d’appels sortants et les stratégies de voix entreprise de Lync Server 2013 doivent être correctement configurés de sorte que les appels PSTN des clients d’un site de succursale soient acheminés vers la passerelle appropriée.

Les réseaux Wi-Fi subissent généralement plus de pertes de paquets que les réseaux câblés. La récupération de cette perte de paquets n’est habituellement pas très bien supportée par les passerelles. C’est pourquoi nous vous conseillons d’évaluer la qualité d’un réseau Wi-Fi avant de déterminer si le contournement doit être activé pour un sous-réseau sans fil. Il convient également de tenir compte d’un compromis entre diminution de la latence et récupération de perte de paquets. RTAudio, un codec disponible pour les appels qui ne contournent pas le serveur de médiation, convient davantage à la gestion de la perte de paquets.

Une fois que votre structure voix entreprise est en place, la planification de la déviation du trafic multimédia est simple.

  - Si vous avez une topologie centralisée sans liaison de réseau distant vers les sites de succursale, vous pouvez activer le contournement de média car il n’est pas nécessaire d’affiner le contrôle.

  - Si votre topologie distribuée est constituée d’une ou plusieurs régions réseau et de leurs sites de succursale affiliés, déterminez les éléments suivants :
    
      - Si vos homologues de serveur de médiation sont en mesure de prendre en charge les fonctionnalités requises pour le contournement de média.
    
      - Quels sont les sites bien connectés dans chaque région réseau.
    
      - Quelle combinaison de contournement de média et de contrôle d’admission des appels est appropriée pour votre réseau.

Lorsque vous activez le contournement de média, un ID unique de contournement est généré automatiquement pour une région réseau et pour tous les sites réseau sans restrictions de bande passante au sein de cette région. Les sites avec restrictions de bande passante dans la région et les sites connectés à la région sur les liaisons du réseau étendu se voient attribués à chacun un ID de contournement unique.

Lorsqu’un utilisateur appelle le RTC, le serveur de médiation compare l’ID de contournement du sous-réseau client à l’ID de contournement du sous-réseau de passerelle. Si les deux ID de contournement concordent, le contournement de média est utilisé pour l’appel. Si les ID de contournement ne correspondent pas, le média de l’appel doit transiter via le serveur de médiation.

Lorsqu’un utilisateur reçoit un appel depuis le réseau téléphonique commuté, le client de l’utilisateur compare son ID de contournement à celui de la passerelle PSTN. Si les deux ID de contournement correspondent, le média transite directement de la passerelle vers le client, en contournant le serveur de médiation.

Seuls les clients et appareils Lync 2010 ou version ultérieure prennent en charge les interactions de contournement de média avec un serveur de médiation.

<div>


> [!IMPORTANT]  
> En plus d’autoriser le contournement de média global, vous devez autoriser le contournement de média individuellement sur chaque jonction RTC. Si le contournement est autorisé globalement mais ne l’est pas pour une jonction RTC donnée, le contournement de média ne sera invoqué pour aucun appel impliquant cette jonction RTC. En outre, lorsque le contournement de média est défini sur <STRONG>Utiliser les informations de site et de région</STRONG>, vous devez associer tous les sous-réseaux routables aux sites sur lesquels ils se situent. Si un site compte des sous-réseaux routables pour lesquels le contournement n’est pas souhaité, ces sous-réseaux devront être regroupés dans un nouveau site avant d’autoriser le contournement de média. Vous êtes ainsi assuré que les sous-réseaux non routables recevront un ID de contournement distinct.



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

