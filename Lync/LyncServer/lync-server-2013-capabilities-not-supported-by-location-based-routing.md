---
title: 'Lync Server 2013 : fonctionnalités non prises en charge par le routage géodépendant'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capabilities not supported by Location-Based Routing
ms:assetid: c3d54953-a7d6-4465-a6c3-ae411b2d8ea9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994071(v=OCS.15)
ms:contentKeyID: 51803982
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99e28778a8bd299d5ead25220f19b27927a63d44
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044196"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capabilities-not-supported-by-location-based-routing-in-lync-server-2013"></a>Fonctionnalités non prises en charge par le routage géodépendant dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-03-12_

Le routage géodépendant ne s’applique pas aux types d’interactions suivants. Le routage géodépendant n’est pas appliqué lorsque les points de terminaison Lync interagissent avec les points de terminaison RTC à l’aide de ces fonctionnalités.

  - Numérotation RTC pour les conférences

  - Appels RTC entrants et sortants via Response Group

  - Parcage d’appel ou récupération des appels PSTN via le parcage d’appel

  - Appels RTC entrants vers le service d’annonce

  - Appels RTC entrants récupérés via la prise d’appel de groupe

Pour appliquer les règles de routage basées sur l’emplacement aux types d’interactions dans la liste suivante, vous devez activer le routage géodépendant pour les conférences :

  - Numérotation RTC des conférences

  - Escalades à partir de conversations audio P2P vers des conférences impliquant des points de terminaison PSTN

  - Transferts consultatifs impliquant des points de terminaison PSTN

Pour activer le routage géodépendant pour les conférences, voir [routage géodépendant pour les conférences dans Lync Server 2013](lync-server-2013-location-based-routing-for-conferencing.md).

<div>

## <a name="see-also"></a>Voir aussi


[Planification du routage géodépendant dans Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

