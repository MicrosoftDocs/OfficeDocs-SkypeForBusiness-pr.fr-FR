---
title: 'Lync Server 2013 : emplacement de la passerelle RTC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN gateway's location
ms:assetid: 49693a35-fad3-49ee-a71e-c7e4537b79aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994031(v=OCS.15)
ms:contentKeyID: 51803940
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef9c58115349e8fedaf25d6f8bc4e1991b65a963
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152308"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="pstn-gateways-location-in-lync-server-2013"></a>Emplacement de la passerelle PSTN dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-09_

Les appels acheminés via des passerelles PSTN et des PBX peuvent nécessiter des restrictions de routage basées sur l’emplacement en fonction de l’emplacement de ces systèmes. Le routage géodépendant peut être activé au niveau de la granularité par tronçon.

Le routage géodépendant présente l’ensemble de règles suivant lorsqu’il est activé sur une jonction :

  - Lorsque le routage géodépendant est activé par tronçon, les règles définies sur cette jonction ne seront appliquées qu’aux appels routés via cette jonction.

  - Pour empêcher le contournement des péages RTC où les appels proviennent d’un site réseau différent du site réseau où se trouve la passerelle PSTN, le routage géodépendant présente l’Association d’un site réseau à une jonction donnée. Cela définit le site réseau qui permet de router les appels vers une jonction donnée.

Les jonctions peuvent être activées pour le routage géodépendant de deux manières :

  - La jonction est définie pour une passerelle RTC qui egresses appelle le RTC. Les appels entrants routés par une jonction de ce type sont acheminés uniquement vers les points de terminaison situés au sein du même site réseau que la jonction.

  - La jonction est définie pour un homologue de serveur de médiation qui ne sort pas les appels vers le réseau téléphonique commuté (RTC) et les utilisateurs de services avec des téléphones hérités dans un emplacement statique (par exemple, téléphones PBX). Pour cette configuration particulière, tous les appels entrants routés par une jonction de ce type sont considérés comme provenant du même site réseau que la jonction. Les appels des utilisateurs PBX auront la même mise en œuvre du routage géodépendant que les utilisateurs Lync qui se trouvent sur le même site réseau que la jonction. Si deux systèmes PBX situés dans des sites réseau distincts sont connectés via Lync Server, le routage géodépendant permet le routage à partir d’un point de terminaison PBX d’un site réseau vers un autre point de terminaison PBX dans l’autre site réseau. Ce scénario ne sera pas bloqué par le routage géodépendant. En plus de ce scénario et de la même manière qu’un utilisateur Lync au même emplacement, les points de terminaison connectés à un serveur de médiation homologue avec cette configuration peuvent passer ou recevoir des appels vers et à partir d’autres homologues de serveur de médiation qui n’acheminent pas les appels vers le RTC (i. e. un point de terminaison connecté à un autre PBX, quel que soit le site réseau auquel l’homologue de serveur de médiation est associé. Tous les appels entrants, sortants, de transfert d’appel et de transfert d’appels impliquant des points de terminaison PSTN seront soumis à un routage basé sur l’emplacement afin d’utiliser uniquement les passerelles PSTN définies comme locales à un tel homologue de serveur de médiation.

<div>

## <a name="see-also"></a>Voir aussi


[Conseils pour le routage géodépendant dans Lync Server 2013](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

