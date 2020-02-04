---
title: 'Lync Server 2013 : tblChat'
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
ms.openlocfilehash: 1f3879924b37fa535973116af599f4713c58a207
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764220"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblchat-in-lync-server-2013"></a>tblChat dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-12_

tblChat contient tous les messages de discussion.

### <a name="columns"></a>Celles

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
<td><p>ent, non null</p></td>
<td><p>ID du nœud.</p></td>
</tr>
<tr class="even">
<td><p>chatId</p></td>
<td><p>bigint, pas null</p></td>
<td><p>Numéro séquentiel unique (par ID de nœud) qui définit l’ordre des salles de conversation généré par la table tblLastChatId.</p></td>
</tr>
<tr class="odd">
<td><p>chatDate</p></td>
<td><p>bigint, pas null</p></td>
<td><p>Horodatage du message.</p></td>
</tr>
<tr class="even">
<td><p>userId</p></td>
<td><p>ent, non null</p></td>
<td><p>ID principal de l’affiche.</p></td>
</tr>
<tr class="odd">
<td><p>isAlert</p></td>
<td><p>bit, pas null</p></td>
<td><p>True si le message est un message d’alerte. Faux si ce n’est pas le cas.</p></td>
</tr>
<tr class="even">
<td><p>teneur</p></td>
<td><p>nvarchar (max), pas null</p></td>
<td><p>Contenu de la discussion (version en texte brut). Le contenu est généralement au format texte brut avec les exceptions suivantes :</p>
<ul>
<li><p>Les fichiers sont représentés par ma-filelink : links.</p></li>
<li><p>Les liens sont représentés sous forme d’élément HTML (même si le type de contenu ne peut pas être considéré comme du code HTML).</p></li>
<li><p>Les récits sont encodés en tant que format « [histoire].... ».</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>RTF</p></td>
<td><p>varchar (max)</p></td>
<td><p>Contenu de conversation (version RTF). Est susceptible d’être null si le client ne la fournit pas.</p></td>
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

