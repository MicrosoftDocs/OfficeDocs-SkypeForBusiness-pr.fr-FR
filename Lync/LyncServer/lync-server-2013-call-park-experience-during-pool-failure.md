---
title: 'Lync Server 2013 : Expérience de parcage d’appel en cas de défaillance d’un pool'
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
ms.openlocfilehash: 59de3b7cc7490c84536cfbc1457c6486af52c33a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742964"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-park-experience-in-lync-server-2013-during-pool-failure"></a>Expérience de parcage d’appel dans Lync Server 2013 en cas de défaillance d’un pool

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-10_

Lorsqu’un pool frontal devient indisponible en raison d’un incident imprévu, les appels qui ont été emportés mais qui ne sont pas encore récupérés sont déconnectés. Pendant le basculement vers un pool de sauvegarde, les utilisateurs sont redirigés vers le pool de sauvegarde et sont en mode de résilience. Lorsque le mode de résilience est activé, les utilisateurs ne peuvent pas parcr les appels, mais ils peuvent placer des appels en attente et les transférer. Lorsque le basculement est terminé, les appels peuvent être de nouveau au parking et extraits comme d’habitude. Pendant la restauration automatique, les utilisateurs ne peuvent pas parcr les appels tant qu’ils ne sont pas en mode de résilience.

Lors de la récupération d’urgence, les utilisateurs qui ont été redirigés vers le pool de sauvegarde dans le cadre du processus de basculement utilisent l’application de parc d’appels qui est déployée dans le pool de sauvegarde. C’est pourquoi les utilisateurs qui sont redirigés vers le pool de sauvegarde utilisent les paramètres de parc d’appels configurés pour l’application de parc d’appels dans le pool de sauvegarde.

Le tableau suivant récapitule le parc d’appels lors de la phase de reprise après sinistre.

### <a name="user-experience-during-disaster-recovery"></a>Utilisation de l’utilisateur pendant une reprise après sinistre

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
<th>Lorsque la panne se produit</th>
<th>Lors du basculement</th>
<th>Durant la restauration automatique</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Appel n’a pas encore été immobilisé</p></td>
<td><p>L’appel reste connecté, mais ne peut pas être parqué.</p></td>
<td><ul>
<li><p>Pendant le basculement, l’appel ne peut pas être parqué lorsque les utilisateurs sont en mode de résilience, mais qui peuvent être mis en attente et transférés.</p></li>
<li><p>Lorsque le basculement est terminé, l’appel peut être parqué et récupéré.</p></li>
</ul></td>
<td><ul>
<li><p>Pendant la restauration, l’appel ne peut pas être parqué tant que les utilisateurs sont en mode de résilience, mais ils peuvent être mis en attente et transférés.</p></li>
<li><p>Lorsque la restauration automatique se termine, l’appel peut être parqué et récupéré.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Appel en stationnement, mais pas encore récupéré</p></td>
<td><p>L’appel est déconnecté.</p></td>
<td><p>Aucun appel dans cet État.</p></td>
<td><p>L’appel reste en stationnement.</p></td>
</tr>
<tr class="odd">
<td><p>Appel parqué déjà récupéré</p></td>
<td><p>L’appel reste connecté.</p></td>
<td><p>L’appel reste connecté.</p></td>
<td><p>L’appel reste connecté.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

