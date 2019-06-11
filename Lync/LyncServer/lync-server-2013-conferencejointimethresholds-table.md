---
title: 'Tableau Lync Server 2013: ConferenceJoinTimeThresholds'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceJoinTimeThresholds table
ms:assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204809(v=OCS.15)
ms:contentKeyID: 48183855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66793cc3bd545d343198d00f7fb477c1f9b88fac
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838489"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencejointimethresholds-table-in-lync-server-2013"></a>Table ConferenceJoinTimeThresholds dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-28_

La table ConferenceJoinTimeThresholds contient les limites de classification utilisées par le rapport de synthèse des heures de participation à la Conférence. Le rapport Résumé de l’heure de la Conférence résume le temps nécessaire pour que les utilisateurs puissent rejoindre une conférence; ces valeurs d’heure sont communiquées tant en moyenne qu’à l’une des catégories suivantes:

  - Moins de 2 secondes.

  - Entre 2 secondes et 5 secondes.

  - Entre 5 et 10 secondes.

  - Plus de 10 secondes.

La table ConferenceJoinTimeThresholds contient les valeurs de classification 2 secondes, 5 secondes et 10 secondes.

Ce tableau a été présenté dans Microsoft Lync Server 2013.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Colonne</th>
<th>Type de données</th>
<th>Clé/Index</th>
<th>Détails</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ThresholdId</strong></p></td>
<td><p>int</p></td>
<td><p>Principal</p></td>
<td><p>Identificateur unique de la classification.</p></td>
</tr>
<tr class="even">
<td><p><strong>ThresholdValue</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Limite supérieure de la classification. Les valeurs autorisées sont les suivantes :</p>
<ol>
<li><p>2</p></li>
<li><p>5</p></li>
<li><p>0,10</p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

