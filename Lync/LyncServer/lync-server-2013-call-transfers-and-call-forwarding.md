---
title: 'Lync Server 2013 : transferts d’appels et transfert d’appel'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call transfers and call forwarding
ms:assetid: 978610ec-63c7-4cf6-ad7a-9ef91559bf12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994051(v=OCS.15)
ms:contentKeyID: 51803962
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de2d258b5820c95b346c76fb5ee7e47e9749c617
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134840"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-transfers-and-call-forwarding-in-lync-server-2013"></a>Transferts d’appels et transfert d’appel dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-09_

Lorsqu’un point de terminaison PSTN est impliqué, le routage géodépendant analyse l’emplacement du point de terminaison du Calle et le point de terminaison vers lequel l’appel sera transféré ou transféré (c.-à-d. cible de transfert/transfert). Routage géodépendant détermine si l’appel doit être transféré ou transféré en fonction de l’emplacement des deux points de terminaison.

Le tableau suivant illustre le scénario d’un utilisateur Lync dans un appel avec un point de terminaison PSTN, et l’utilisateur Lync transfère l’appel vers un autre utilisateur Lync. En fonction de l’emplacement du site réseau du point de terminaison du cessionnaire, le routage géodépendant a une incidence sur le routage du transfert d’appel ou vers l’aval.

### <a name="initiating-call-transfer-or-forward"></a>Lancement du transfert ou du transfert d’appel

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Utilisateur lançant le transfert/transfert d’appel</th>
<th>Le point de terminaison cible se trouve dans le même site réseau que l’utilisateur à l’origine du transfert ou du transfert d’appel</th>
<th>Le point de terminaison cible se trouve dans un autre site réseau que l’utilisateur à l’origine du transfert ou du transfert d’appel</th>
<th>Le point de terminaison cible se trouve dans un site réseau inconnu ou le site réseau n’est pas activé pour le routage géodépendant</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Utilisateur Lync</p></td>
<td><p>Le transfert d’appel ou le transfert est autorisé</p></td>
<td><p>Le transfert d’appel ou le transfert n’est pas autorisé</p></td>
<td><p>Le transfert d’appel ou le transfert n’est pas autorisé</p></td>
</tr>
</tbody>
</table>

  

Par exemple : un utilisateur Lync dans un appel avec un point de terminaison PSTN transfère l’appel vers un autre utilisateur Lync qui se trouve dans le même site réseau. Dans ce cas, le transfert d’appel est autorisé.

Le tableau suivant illustre le scénario d’un utilisateur Lync dans un appel avec un autre utilisateur Lync, et l’un des utilisateurs transfère l’appel vers un point de terminaison PSTN. En fonction de l’emplacement de l’utilisateur vers lequel l’appel est transféré, le tableau explique en détail comment le routage géodépendant affecte l’appel.

### <a name="call-transfer-or-forward-to-pstn-endpoint"></a>Transfert d’appel ou transfert vers le point de terminaison PSTN

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Cible de point de terminaison/transfert d’appel</th>
<th>Utilisateurs Lync dans le même site réseau</th>
<th>Utilisateurs Lync dans différents sites réseau</th>
<th>Un ou les deux utilisateurs Lync dans un site réseau inconnu ou un site réseau non activé pour le routage géodépendant</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Point de terminaison PSTN</p></td>
<td><p>Transfert d’appel ou transfert autorisé par la stratégie de routage des communications vocales du site de l’utilisateur transféré</p></td>
<td><p>Transfert d’appel ou transfert autorisé par la stratégie de routage des communications vocales du site de l’utilisateur transféré</p></td>
<td><p>Transfert d’appel ou transfert autorisé par la stratégie de voix de l’utilisateur transféré uniquement via des jonctions non activées pour le routage géodépendant</p></td>
</tr>
</tbody>
</table>

  
Par exemple : un utilisateur Lync dans un appel avec un autre utilisateur Lync qui se trouve sur le même site réseau transfère l’appel vers un point de terminaison PSTN et le transfert d’appel est autorisé.

<div>

## <a name="see-also"></a>Voir aussi


[Scénarios de routage géodépendant dans Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

