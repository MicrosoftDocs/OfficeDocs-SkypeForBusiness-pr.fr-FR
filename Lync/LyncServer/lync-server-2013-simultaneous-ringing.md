---
title: 'Lync Server 2013 : Sonnerie simultanée'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Simultaneous ringing
ms:assetid: df02f919-4d50-4832-9300-6c51f8b4fc56
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994079(v=OCS.15)
ms:contentKeyID: 51803990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7303c1fc77d109bd08044c8acff56aaf538790d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846820"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="simultaneous-ringing-in-lync-server-2013"></a>Sonnerie simultanée dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-03-09_

Lorsque la partie appelée dispose d’une sonnerie simultanée activée, le routage de géolocalisation analyse l’emplacement de la partie de l’appel et les points de terminaison des parties appelées pour déterminer si l’appel doit être routé.

Le tableau ci-dessous illustre un utilisateur pour lequel la sonnerie simultanée est configurée. La cible de la sonnerie simultanée est un utilisateur appartenant au même site réseau, à un autre site réseau ou à un site réseau inconnu.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Appel RTC entrant pour</th>
<th>Situé dans le même site réseau que l’appelé</th>
<th>Situé dans un autre site réseau que l’appelé</th>
<th>Se trouve sur un site réseau inconnu ou n’est pas activé pour le routage par emplacement</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Utilisateur Lync</p></td>
<td><p>Sonnerie simultanée autorisée</p></td>
<td><p>Sonnerie simultanée non autorisée</p></td>
<td><p>Sonnerie simultanée non autorisée</p></td>
</tr>
</tbody>
</table>

  
Le tableau suivant illustre un appel d’un utilisateur Lync (par exemple, appelant Lync) au sein d’un même site réseau, sur un autre site réseau ou à partir d’un site réseau inconnu. L’appelé a un point de terminaison RTC (téléphone portable) configuré comme cible de la sonnerie simultanée. Dans ce scénario, le routage en fonction de l’emplacement détermine si l’appel doit être acheminé vers la cible de sonnerie simultanée (c.-à-d. téléphone mobile) de l’appelé ou non.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Cible de la sonnerie simultanée</th>
<th>Situé dans le même site réseau que l’appelé</th>
<th>Situé dans un autre site réseau que l’appelé</th>
<th>Se trouve sur un site réseau inconnu ou n’est pas activé pour le routage par emplacement</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Point de terminaison RTC</p></td>
<td><p>Sonnerie simultanée autorisée via la stratégie de routage des communications vocales du site de l’appelant</p></td>
<td><p>Sonnerie simultanée autorisée via la stratégie de routage des communications vocales du site de l’appelant</p></td>
<td><p>Sonnerie simultanée autorisée via la stratégie de voix de l’appelant vers les jonctions sur lesquelles le routage géodépendant n’est pas activé</p></td>
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

