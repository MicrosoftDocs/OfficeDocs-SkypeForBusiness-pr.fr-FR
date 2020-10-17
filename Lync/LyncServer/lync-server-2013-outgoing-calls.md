---
title: 'Lync Server 2013 : appels sortants'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Outgoing calls
ms:assetid: 885ffe6f-cd51-4f21-8d4f-a1ff8d818858
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994049(v=OCS.15)
ms:contentKeyID: 51803960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a77ddf0757cd463bb8f1b95dbecfe90fd1086c9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524401"
---
# <a name="outgoing-calls-in-lync-server-2013"></a>Appels sortants dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-09_

Le routage des appels sortants d’utilisateurs activés pour le routage des Location-Based est affecté par l’emplacement réseau du point de terminaison de l’utilisateur. Le tableau suivant montre comment Location-Based routage affecte le routage des appels sortants en fonction de l’emplacement du point de terminaison de l’appelant.

### <a name="caller-placing-an-outbound-call-to-the-pstn"></a>Appelant passant un appel sortant vers le réseau téléphonique commuté (RTC)

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Point de terminaison d’utilisateur situé dans un site réseau activé pour le routage des Location-Based</th>
<th>Point de terminaison de l’utilisateur situé dans un site réseau inconnu ou non activé pour le routage des Location-Based</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Autorisation des appels sortants</p></td>
<td><p>L’appel est autorisé en fonction de la stratégie de voix de l’utilisateur</p></td>
<td><p>L’appel est autorisé en fonction de la stratégie de voix de l’utilisateur</p></td>
</tr>
<tr class="even">
<td><p>Routage des appels sortants</p></td>
<td><p>L’appel est acheminé en fonction de la stratégie de routage des communications vocales du site réseau</p></td>
<td><p>L’appel est acheminé en fonction de la stratégie de voix de l’utilisateur et uniquement via des jonctions non activées pour le routage des Location-Based (le cas échéant)</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>Voir aussi


[Scénarios de routage des Location-Based dans Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

