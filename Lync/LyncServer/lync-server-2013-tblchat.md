---
title: 'Lync Server 2013 : tblChat'
TOCTitle: tblChat
ms:assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg615031(v=OCS.15)
ms:contentKeyID: 49298642
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblChat dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

tblChat contient tous les messages de conversation.

### Colonnes

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
<td><p>content</p></td>
<td><p>nvarchar (max), non null</p></td>
<td><p>Contenu de la conversation (version en texte brut). Le contenu est généralement en texte brut, avec les exceptions suivantes :</p>
<ul>
<li><p>les fichiers sont représentés sous forme de liens ma-filelink: ;</p></li>
<li><p>les liens sont représentés sous forme d’éléments HTML (même si le type de contenu ne peut pas être considéré comme du HTML) ;</p></li>
<li><p>Les articles sont encodés au format « [STORY].... ».</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>rtf</p></td>
<td><p>varchar(max)</p></td>
<td><p>Contenu de la conversation (version au format RTF). Peut être Null si le client ne le fournit pas.</p></td>
</tr>
</tbody>
</table>


### Clé

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
<td><p>&lt;channelID, chatD&gt;</p></td>
<td><p>Clé primaire.</p></td>
</tr>
</tbody>
</table>

