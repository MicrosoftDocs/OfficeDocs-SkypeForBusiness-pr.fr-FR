---
title: 'Lync Server 2013 : tblEnumValue'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblEnumValue
ms:assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615025(v=OCS.15)
ms:contentKeyID: 48185040
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d182a3689ae38d4117b45d6590bb2ccd08c0a8b7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42027055"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblenumvalue-in-lync-server-2013"></a>tblEnumValue dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-06-28_

tblEnumValue est une table codée en dur qui contient les valeurs Visibilité et Comportement des attributs utilisés dans la table Node.

### <a name="columns"></a>Columns

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Colonne</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>valueID</p></td>
<td><p>smallint, non null</p></td>
<td><p>ID de la valeur</p></td>
</tr>
<tr class="even">
<td><p>attributeID</p></td>
<td><p>smallint, non null</p></td>
<td><p>ID de l’attribut</p></td>
</tr>
<tr class="odd">
<td><p>attributeValue</p></td>
<td><p>nvarchar (256), non null</p></td>
<td><p>Nom de la valeur.</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>Keys

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Colonne</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>valueID</p></td>
<td><p>Clé primaire.</p></td>
</tr>
<tr class="even">
<td><p>attributeID</p></td>
<td><p>Clé étrangère avec recherche dans la table tblEnumAttribute.attributeID.</p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a>Valeurs de la table

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>valueID</th>
<th>attributeID</th>
<th>attributeValue</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2 </p></td>
<td><p>1 </p></td>
<td><p>privé</p></td>
</tr>
<tr class="even">
<td><p>3 </p></td>
<td><p>1 </p></td>
<td><p>portée</p></td>
</tr>
<tr class="odd">
<td><p>4 </p></td>
<td><p>2 </p></td>
<td><p>anormal</p></td>
</tr>
<tr class="even">
<td><p>5 </p></td>
<td><p>2 </p></td>
<td><p>Auditorium</p></td>
</tr>
<tr class="odd">
<td><p>6 </p></td>
<td><p>1 </p></td>
<td><p>libre</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>Voir aussi


[tblNode dans Lync Server 2013](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

