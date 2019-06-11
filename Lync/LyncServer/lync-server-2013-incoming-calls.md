---
title: 'Lync Server 2013 : Appels entrants'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Incoming calls
ms:assetid: 65b9c1b4-6af7-4527-8c33-22c4442bd209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994038(v=OCS.15)
ms:contentKeyID: 51803948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c007fbaec317a8e9d9d374ea62dafcab6c7a63f4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831015"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="incoming-calls-in-lync-server-2013"></a>Appels entrants dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-03-09_

Le routage des appels entrants vers les utilisateurs activés pour le routage par emplacement dépend de l’emplacement du point de terminaison de l’utilisateur. Le routage des appels entrants est affecté comme suit. Si un utilisateur dispose d’un appel entrant à un point de terminaison situé dans un site réseau de routage de géolocalisation et que le point de terminaison se trouve sur le même site réseau que la passerelle RTC, l’appel est routé. Si un utilisateur dispose d’un appel entrant vers un point de terminaison situé dans un site réseau compatible avec le routage d’emplacement et que le point de terminaison se trouve dans un autre site réseau que la passerelle RTC, l’appel n’est pas acheminé. Lorsqu’un utilisateur n’a pas de points de terminaison situés dans le même site réseau que la passerelle RTC à partir de laquelle l’appel entrant provient, l’appel entrant est acheminé directement vers la messagerie vocale de l’utilisateur et une notification d’appel manqué est envoyée à la personne appelée.

Les paramètres de transfert d’appel d’un utilisateur qui est autorisé à utiliser le routage de géolocalisation continuent d’être appliqués, toutefois, les appels transférés seront soumis à des restrictions de routage basées sur l’emplacement de l’utilisateur.

Le tableau suivant illustre la façon dont le routage en fonction de l’emplacement affecte le routage des appels entrants en fonction de l’emplacement du point de terminaison de l’appelant. Le site réseau de la passerelle RTC est activé pour le routage d’emplacement et le routage basé sur l’emplacement autorise uniquement le routage des appels RTC vers des points de terminaison au sein du même site réseau.

### <a name="callee-receiving-an-inbound-call-from-the-pstn"></a>Appelé recevant un appel entrant à partir de la passerelle RTC

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Point de terminaison de l’appelé situé dans le même site réseau que la passerelle RTC</th>
<th>Point de terminaison de l’appelé non situé dans le même site réseau que la passerelle RTC</th>
<th>Point de terminaison de l’appelé situé dans un site réseau inconnu ou pour lequel le routage géodépendant n’est pas activé</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Routage de l’appel RTC entrant</p></td>
<td><p>L’appel entrant est routé vers les points de terminaison de l’appelé</p></td>
<td><p>L’appel entrant n‘est pas routé vers les points de terminaison de l’appelé</p></td>
<td><p>L’appel entrant n‘est pas routé vers les points de terminaison de l’appelé</p></td>
</tr>
</tbody>
</table>

  

<div>

## <a name="see-also"></a>Voir aussi


[Scénarios de routage géodépendant dans Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

