---
title: 'Lync Server 2013 : Appels sortants'
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
ms.openlocfilehash: 1a353cecbf1cdc1ff411c2cfe7c57edcd909c5c8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755638"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="outgoing-calls-in-lync-server-2013"></a>Appels sortants dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-09_

Le routage des appels sortants d’utilisateurs activés pour le routage par emplacement est affecté par l’emplacement réseau du point de terminaison de l’utilisateur. Le tableau suivant illustre la façon dont le routage en fonction de l’emplacement affecte le routage des appels sortants en fonction de l’emplacement du point de terminaison de l’appelant.

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
<th>Point de terminaison d’un utilisateur situé dans un site réseau pour lequel le routage géodépendant est activé</th>
<th>Point de terminaison de l’utilisateur situé dans un site réseau inconnu ou pour lequel le routage géodépendant n’est pas activé</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Autorisation des appels sortants</p></td>
<td><p>L’appel est autorisé sur la base de la stratégie de voix de l’utilisateur</p></td>
<td><p>L’appel est autorisé sur la base de la stratégie de voix de l’utilisateur</p></td>
</tr>
<tr class="even">
<td><p>Routage de l’appel sortant</p></td>
<td><p>L’appel est routé selon le stratégie de routage des communications vocales du site réseau</p></td>
<td><p>L’appel est routé selon la stratégie de voix de l’utilisateur en utilisant uniquement des jonctions pour lesquelles le routage géodépendant n’est pas activé (si celui-ci est disponible)</p></td>
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

