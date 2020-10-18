---
title: 'Lync Server 2013 : tblChat'
description: 'Lync Server 2013 : tblChat.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblChat
ms:assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615031(v=OCS.15)
ms:contentKeyID: 48185203
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e68d4f0d1ca7ae227c78c95d02e02ffc81656feb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573650"
---
# <a name="tblchat-in-lync-server-2013"></a>tblChat dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-12_

tblChat contient tous les messages de conversation.

### <a name="columns"></a>Colonnes

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
<td><p>channelId</p></td>
<td><p>int, non null</p></td>
<td><p>ID de nœud.</p></td>
</tr>
<tr class="even">
<td><p>chatId</p></td>
<td><p>bigint, non null</p></td>
<td><p>Numéro d’ordre unique (par ID de nœud) qui définit l’ordre de la salle de conversation, généré par la table tblLastChatId.</p></td>
</tr>
<tr class="odd">
<td><p>chatDate</p></td>
<td><p>bigint, non null</p></td>
<td><p>Horodatage du message de conversation.</p></td>
</tr>
<tr class="even">
<td><p>userId</p></td>
<td><p>int, non null</p></td>
<td><p>ID de principal de la personne ayant publié le message.</p></td>
</tr>
<tr class="odd">
<td><p>isAlert</p></td>
<td><p>bit, non null</p></td>
<td><p>True s’il s’agit d’un message d’alerte. False dans le cas contraire.</p></td>
</tr>
<tr class="even">
<td><p>contenu</p></td>
<td><p>nvarchar (max), non null</p></td>
<td><p>Contenu de la conversation (version en texte brut). Le contenu est généralement en texte brut, avec les exceptions suivantes :</p>
<ul>
<li><p>les fichiers sont représentés sous forme de liens ma-filelink: ;</p></li>
<li><p>les liens sont représentés sous forme d’éléments HTML (bien que le type de contenu ne puisse pas être considéré comme du HTML) ;</p></li>
<li><p>Les articles sont encodés au format « [STORY].... ».</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>formats</p></td>
<td><p>varchar (max)</p></td>
<td><p>Contenu de la conversation (version au format RTF). Peut être Null si le client ne le fournit pas.</p></td>
</tr>
</tbody>
</table>


### <a name="key"></a>Clé

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
<td><p>&lt;channelID, conversation&gt;</p></td>
<td><p>Clé primaire.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

