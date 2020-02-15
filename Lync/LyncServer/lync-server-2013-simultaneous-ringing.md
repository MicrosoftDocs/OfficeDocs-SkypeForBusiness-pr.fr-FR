---
title: 'Lync Server 2013 : sonnerie simultanée'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Simultaneous ringing
ms:assetid: df02f919-4d50-4832-9300-6c51f8b4fc56
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994079(v=OCS.15)
ms:contentKeyID: 51803990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e3104da5e7d351bda26698087e97106cafbdff4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037504"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="simultaneous-ringing-in-lync-server-2013"></a>Sonnerie simultanée dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-09_

Lorsque le composant appelé dispose d’une sonnerie simultanée, le routage géodépendant permet d’analyser l’emplacement de l’appelant et les points de terminaison des parties appelées afin de déterminer si l’appel doit être acheminé.

Le tableau suivant illustre un utilisateur configuré avec la sonnerie simultanée et la cible de la sonnerie simultanée est un utilisateur du même site réseau, d’un site réseau différent ou d’un site réseau inconnu.


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
<th>Situé dans le même site réseau que l’appelé.</th>
<th>Situé dans un site réseau différent de celui de l’appelé ;</th>
<th>Situé dans un site réseau inconnu ou non activé pour le routage géodépendant</th>
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

  
Le tableau suivant illustre un appel d’un utilisateur Lync (par exemple, l’appelant Lync) dans le même site réseau, dans un autre site réseau ou à partir d’un site réseau inconnu. L’appelé a un point de terminaison PSTN (par exemple, téléphone portable) configuré en tant que cible circulaire simultanée. Dans ce scénario, le routage géodépendant indique si l’appel doit être acheminé vers la cible de sonnerie simultanée (téléphone cellulaire) de l’appelé ou non.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Cible annulaire simultanée</th>
<th>Situé dans le même site réseau que l’appelé.</th>
<th>Situé dans un site réseau différent de celui de l’appelé ;</th>
<th>Situé dans un site réseau inconnu ou non activé pour le routage géodépendant</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Point de terminaison PSTN</p></td>
<td><p>Sonnerie simultanée autorisée via la stratégie de routage des communications vocales du site de l’appelant</p></td>
<td><p>Sonnerie simultanée autorisée via la stratégie de routage des communications vocales du site de l’appelant</p></td>
<td><p>Sonnerie simultanée autorisée via la stratégie de voix de l’appelant aux jonctions non activées pour le routage géodépendant</p></td>
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

