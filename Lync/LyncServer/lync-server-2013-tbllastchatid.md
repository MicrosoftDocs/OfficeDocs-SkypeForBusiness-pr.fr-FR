---
title: 'Lync Server 2013 : tblLastChatId'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblLastChatId
ms:assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558616(v=OCS.15)
ms:contentKeyID: 48183513
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be10514a933cb6a311d115fbbb011398f2758ef9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42025575"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbllastchatid-in-lync-server-2013"></a>tblLastChatId dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-12_

tblLastChatId contient le dernier ID de conversation généré (et utilisé dans la table tblChat) pour chaque utilisateur.

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
<td><p>nodeID</p></td>
<td><p>int, non null</p></td>
<td><p>ID de nœud (type de salle de conversation seulement).</p></td>
</tr>
<tr class="even">
<td><p>lastChatID</p></td>
<td><p>bigint, non null</p></td>
<td><p>ID de conversation le plus récemment utilisé.</p></td>
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
<td><p>&lt;nodeID, lastChatID&gt;</p></td>
<td><p>Clé principale (nodeID est suffisant pour le traitement).</p></td>
</tr>
<tr class="even">
<td><p>nodeID</p></td>
<td><p>Clé étrangère avec recherche dans la table tblNode.nodeID.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>Voir aussi


[tblChat dans Lync Server 2013](lync-server-2013-tblchat.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

