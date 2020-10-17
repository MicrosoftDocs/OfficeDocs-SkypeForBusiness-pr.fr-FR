---
title: 'Lync Server 2013 : table table callpriorities'
description: 'Lync Server 2013 : table table callpriorities.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: CallPriorities table
ms:assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398093(v=OCS.15)
ms:contentKeyID: 48183275
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe3cd1639921c63630e157744dbc8af22c50fac7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565180"
---
# <a name="callpriorities-table-in-lync-server-2013"></a>Table table callpriorities dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-28_

La table CallPriorities est une table statique qui stocke la liste des priorités d’appel possibles, par exemple « très urgent », « urgent » ou « normal ».


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
<th>Clé/index</th>
<th>Détails</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>PriorityId</strong></p></td>
<td><p>entier très petit</p></td>
<td><p>Primaire</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><strong>Priorité</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td></td>
<td><p>Valeurs autorisées :</p>
<ul>
<li><p>0 - Inconnu</p></li>
<li><p>1 – Non urgent</p></li>
<li><p>2 - Normal</p></li>
<li><p>3 - Urgent</p></li>
<li><p>4 - Très urgent</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

