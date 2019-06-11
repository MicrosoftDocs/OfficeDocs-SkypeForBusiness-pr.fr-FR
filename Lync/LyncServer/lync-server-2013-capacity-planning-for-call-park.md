---
title: 'Lync Server 2013 : Planification de capacité pour le parcage d’appel'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capacity planning for Call Park
ms:assetid: 75520310-760a-4b1b-bcc1-4d724d13f87a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416493(v=OCS.15)
ms:contentKeyID: 48184529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5fe55e09c67e62676202def9e3def3454d7cbd33
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838677"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-call-park-in-lync-server-2013"></a>Planification de capacité pour le parcage d’appel dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-13_

<div id="sectionSection0" class="section">

Le tableau suivant décrit le modèle d’utilisateur de parc d’appels que vous pouvez utiliser comme base pour les exigences de planification de capacité.

<div>


> [!IMPORTANT]  
> Gardez à l’esprit que pour la planification de la capacité de reprise après sinistre, chaque pool d’un pool couplé doit être en mesure de gérer les charges de travail des services de parc d’appels dans les deux pools.



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
<th>Mesure</th>
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

