---
title: 'Lync Server 2013 : appels entrants'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Incoming calls
ms:assetid: 65b9c1b4-6af7-4527-8c33-22c4442bd209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994038(v=OCS.15)
ms:contentKeyID: 51803948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb8be496e863058ddec27dd92b994d94b86a26e2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147247"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="incoming-calls-in-lync-server-2013"></a>Appels entrants dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-09_

Le routage des appels entrants vers des utilisateurs activés pour le routage géodépendant dépend de l’emplacement du point de terminaison de l’utilisateur. Le routage des appels entrants est affecté de la manière suivante. Si un utilisateur a reçu un appel entrant vers un point de terminaison situé dans un site réseau de routage basé sur l’emplacement et que le point de terminaison se trouve dans le même site réseau que la passerelle RTC, l’appel sera acheminé. Si un utilisateur a reçu un appel entrant vers un point de terminaison situé dans un site réseau de routage basé sur l’emplacement et que le point de terminaison se trouve dans un autre site réseau que la passerelle RTC, l’appel n’est pas acheminé. Lorsqu’un utilisateur n’a pas de point de terminaison situé dans le même site réseau que la passerelle RTC, l’appel entrant est acheminé directement vers la messagerie vocale de l’utilisateur et une notification d’appel en absence est envoyée à la personne appelée.

Les paramètres de transfert d’appel d’un utilisateur activé pour le routage géodépendant continueront à être appliqués, cependant, les appels transférés seront soumis aux restrictions de routage géodépendant de l’utilisateur.

Le tableau suivant montre comment le routage géodépendant affecte le routage des appels entrants en fonction de l’emplacement du point de terminaison de l’appelé. Le site réseau de la passerelle PSTN est activé pour le routage géodépendant et le routage géodépendant uniquement autorise le routage des appels PSTN vers les points de terminaison au sein du même site réseau.

### <a name="callee-receiving-an-inbound-call-from-the-pstn"></a>Appelé recevant un appel entrant du RTC

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
<th>Point de terminaison de l’appelé situé dans le même site réseau que la passerelle PSTN</th>
<th>Point de terminaison de l’appelé non situé dans le même site réseau que la passerelle PSTN</th>
<th>Point de terminaison de l’appelé situé dans un site réseau inconnu ou non activé pour le routage géodépendant</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Routage des appels RTC entrants</p></td>
<td><p>L’appel entrant est acheminé vers les points de terminaison de l’appelé</p></td>
<td><p>L’appel entrant n’est pas acheminé vers les points de terminaison de l’appelé</p></td>
<td><p>L’appel entrant n’est pas acheminé vers les points de terminaison de l’appelé</p></td>
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

