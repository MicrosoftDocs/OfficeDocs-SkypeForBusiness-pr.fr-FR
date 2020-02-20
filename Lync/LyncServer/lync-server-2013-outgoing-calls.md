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
ms.openlocfilehash: 5626e5e60a72967c84a79b6ec9aca818d8d62800
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153314"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="outgoing-calls-in-lync-server-2013"></a>Appels sortants dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-09_

Le routage des appels sortants d’utilisateurs activés pour le routage géodépendant est affecté par l’emplacement réseau du point de terminaison de l’utilisateur. Le tableau suivant montre comment le routage géodépendant affecte le routage des appels sortants en fonction de l’emplacement du point de terminaison de l’appelant.

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
<th>Point de terminaison d’utilisateur situé dans un site réseau activé pour le routage géodépendant</th>
<th>Point de terminaison d’utilisateur situé dans un site réseau inconnu ou non activé pour le routage géodépendant</th>
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
<td><p>L’appel est acheminé en fonction de la stratégie de voix de l’utilisateur et uniquement via des jonctions non activées pour le routage géodépendant (le cas échéant)</p></td>
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

