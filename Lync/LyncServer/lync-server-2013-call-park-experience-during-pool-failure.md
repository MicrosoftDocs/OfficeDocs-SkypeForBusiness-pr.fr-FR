---
title: 'Lync Server 2013 : expérience de parcage d’appel en cas de défaillance du pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Park experience during pool failure
ms:assetid: f6303e69-8771-492a-9e8b-c3d7ba231309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205383(v=OCS.15)
ms:contentKeyID: 48185831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 605900501a141c053459c690292b1e0a10c8abbc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508251"
---
# <a name="call-park-experience-in-lync-server-2013-during-pool-failure"></a>Expérience de parcage d’appel dans Lync Server 2013 en cas de défaillance du pool

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-10_

Lorsqu’un pool frontal devient indisponible en raison d’un incident non planifié, les appels qui ont été parqués mais ne sont pas encore extraits sont déconnectés. Durant le basculement vers un pool de sauvegarde, les utilisateurs sont redirigés vers le pool de sauvegarde et placés en mode Résilience. Dans ce mode, les utilisateurs ne peuvent pas parquer les appels, mais ils peuvent les placer en attente et les transférer. Lorsque le basculement est terminé, les appels peuvent de nouveau être parqués et récupérés, comme d’habitude. Durant la restauration automatique, les utilisateurs ne peuvent pas parquer les appels jusqu’à ce qu’ils quittent le mode Résilience.

Lors de la récupération d’urgence, les utilisateurs qui ont été redirigés vers le pool de sauvegarde dans le cadre du processus de basculement utilisent l’application de parcage d’appel qui est déployée dans le pool de sauvegarde. Par conséquent, les utilisateurs qui sont redirigés vers le pool de sauvegarde utilisent les paramètres de parcage d’appel qui sont configurés pour l’application de parcage d’appel dans le pool de sauvegarde.

Le tableau suivant résume l’expérience de parcage d’appel pendant les phases de récupération d’urgence.

### <a name="user-experience-during-disaster-recovery"></a>Expérience utilisateur durant la récupération d’urgence

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>État de l’appel</th>
<th>Lorsqu’une panne se produit</th>
<th>Durant le basculement</th>
<th>Durant la restauration automatique</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Pour les appels non parqués</p></td>
<td><p>Les appels restent connectés, mais ne peuvent pas être parqués.</p></td>
<td><ul>
<li><p>Durant le basculement, les appels ne peuvent pas être parqués pendant que les utilisateurs sont en mode Résilience, mais ils peuvent être mis en attente et transférés.</p></li>
<li><p>Lorsque le basculement est terminé, les appels peuvent être parqués et récupérés.</p></li>
</ul></td>
<td><ul>
<li><p>Durant la restauration automatique, les appels ne peuvent pas être parqués pendant que les utilisateurs sont en mode Résilience, mais ils peuvent être mis en attente et transférés.</p></li>
<li><p>Lorsque la restauration automatique est terminée, les appels peuvent être parqués et récupérés.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Pour les appels parqués, mais non récupérés</p></td>
<td><p>Ces appels sont déconnectés.</p></td>
<td><p>Aucun appel ne reste dans cet état.</p></td>
<td><p>Les appels restent parqués.</p></td>
</tr>
<tr class="odd">
<td><p>Pour les appels parqués déjà récupérés</p></td>
<td><p>Ces appels restent connectés.</p></td>
<td><p>Ces appels restent connectés.</p></td>
<td><p>Ces appels restent connectés.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

