---
title: 'Lync Server 2013 : délégation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegation
ms:assetid: 89e76e5c-3cfb-4504-8d0d-7509c8ba9815
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994045(v=OCS.15)
ms:contentKeyID: 51803956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57de37ff1ef0b43a8a6ea9c03b715d3ebe570a6b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190907"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delegation-in-lync-server-2013"></a>Délégation dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-09_

Les fonctionnalités de délégation de Lync sont affectées par le routage géodépendant de la manière suivante :

  - Lorsqu’un délégué activé pour le routage géodépendant place un appel au nom d’un responsable, la stratégie de voix du délégué est utilisée pour autoriser l’appel et la stratégie de routage des communications vocales du site délégué sera utilisée pour acheminer l’appel.

  - Pour les appels RTC entrants vers un responsable, les règles applicables au transfert d’appel ou à la sonnerie simultanée s’appliquent comme décrit dans les rubriques transfert d’appel et transfert et sonnerie simultanée.

  - Lorsqu’un délégué définit un point de terminaison PSTN en tant que cible de la sonnerie simultanée, pour un appel entrant vers le responsable, la stratégie de routage des communications vocales du site associé à la jonction entrante est utilisée pour acheminer l’appel vers le point de terminaison PSTN du délégué.

  - Pour la délégation, il est recommandé que le gestionnaire et ses délégués associés soient généralement situés dans le même site réseau.

<div>

## <a name="see-also"></a>Voir aussi


[Scénarios de routage géodépendant dans Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

