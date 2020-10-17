---
title: 'Lync Server 2013 : table ErrorCategory'
description: 'Lync Server 2013 : table ErrorCategory.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorCategory table
ms:assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204675(v=OCS.15)
ms:contentKeyID: 48183425
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8154c73f33b5dad62a338335a960553cfc06ec13
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546430"
---
# <a name="errorcategory-table-in-lync-server-2013"></a>Table ErrorCategory dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-08-20_

La table ErrorCategory contient le nom convivial de chaque classification de diagnostic Microsoft Lync Server 2013. Par défaut, Lync Server 2013 utilise les classifications suivantes :

  - 0 : réussite

  - 1-échec ATTENDU

  - 2 : échec inattendu

Cette table a été introduite dans Microsoft Lync Server 2013.


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
<td><p><strong>CategoryId</strong></p></td>
<td><p>entier très petit</p></td>
<td><p>Primaire</p></td>
<td><p>Identificateur unique pour la classification.</p></td>
</tr>
<tr class="even">
<td><p><strong>Name</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td></td>
<td><p>Valeur et nom convivial attribués à la classification. Les valeurs autorisées sont les suivantes :</p>
<ul>
<li><p>0 : réussite</p></li>
<li><p>1-échec ATTENDU</p></li>
<li><p>2 : échec inattendu</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

