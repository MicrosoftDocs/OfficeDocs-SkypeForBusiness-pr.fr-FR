---
title: 'Lync Server 2013 : planification de la capacité pour le parcage d’appel'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Call Park
ms:assetid: 75520310-760a-4b1b-bcc1-4d724d13f87a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416493(v=OCS.15)
ms:contentKeyID: 48184529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 079d1517afa72eeff607920d86b093ac01d673de
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512831"
---
# <a name="capacity-planning-for-call-park-in-lync-server-2013"></a>Planification de la capacité pour le parcage d’appel dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-13_

<div id="sectionSection0" class="section">

Le tableau suivant décrit le modèle utilisateur de parcage d’appel que vous pouvez utiliser comme base pour les exigences de planification de capacité.

<div>


> [!IMPORTANT]  
> N’oubliez pas que, pour la planification de la capacité de récupération d’urgence, chaque pool d’un pool couplé doit être en mesure de gérer les charges de travail des services de parcage d’appel dans les deux pools.



</div>

### <a name="call-park-user-model"></a>Modèle utilisateur de parcage d’appel

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Métrique</th>
<th>Par pool frontal (avec 8 serveurs frontaux)</th>
<th>Par serveur Standard Edition</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Taux de parcage</p></td>
<td><p>8 par minute</p></td>
<td><p>1 par minute</p></td>
</tr>
<tr class="even">
<td><p>Taux d’appels parqués récupérés</p></td>
<td><p>8 par minute</p></td>
<td><p>1 par minute</p></td>
</tr>
<tr class="odd">
<td><p>Durée moyenne de parcage</p></td>
<td><p>60 secondes</p></td>
<td><p>60 secondes</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

