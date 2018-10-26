---
title: 'Lync Server 2013 : tblComplianceData'
TOCTitle: tblComplianceData
ms:assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg558606(v=OCS.15)
ms:contentKeyID: 49296133
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblComplianceData dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

tblComplianceData contient les événements de conformité qui n’ont pas encore été traités par l’ensemble des convertisseurs inscrits.

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
<td><p>cmplEventID</p></td>
<td><p>bigint, non null</p></td>
<td><p>ID d’événement.</p></td>
</tr>
<tr class="even">
<td><p>entryDate</p></td>
<td><p>smalldatetime, non null</p></td>
<td><p>Moment de l’insertion (peut être éloigné dans le futur pour cmplType=9, car l’entrée est juste un espace réservé dans ce cas).</p></td>
</tr>
<tr class="odd">
<td><p>cmplType</p></td>
<td><p>entier, non null</p></td>
<td><p>Type d’événement de conformité :</p>
<ul>
<li><p>1: Conversation</p></li>
<li><p>2: Sauvegarde de conversation</p></li>
<li><p>3: Téléchargement de fichiers</p></li>
<li><p>4: Chargement de fichiers</p></li>
<li><p>9: Transfert de fichier provisoire</p></li>
<li><p>10: Suppression de conversation (avec remplacement)</p></li>
<li><p>11: Purge des conversations</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>cmplTime</p></td>
<td><p>bigint, non null</p></td>
<td><p>Horodatage pour l’événement.</p></td>
</tr>
<tr class="odd">
<td><p>cmplChannelUri</p></td>
<td><p>nvarchar (255), non null</p></td>
<td><p>URI (Uniform Resource Identifier) du canal.</p></td>
</tr>
<tr class="even">
<td><p>cmplChatID</p></td>
<td><p>bigint</p></td>
<td><p>ID de conversation (correspondant à la table tblChat.chatId).</p></td>
</tr>
<tr class="odd">
<td><p>cmplUserID</p></td>
<td><p>entier, non null</p></td>
<td><p>ID principal de l’affiche (correspondant à la table tblPrincipal.prinID).</p></td>
</tr>
<tr class="even">
<td><p>cmplUserUri</p></td>
<td><p>nvarchar (255), non null</p></td>
<td><p>URI de l’utilisateur.</p></td>
</tr>
<tr class="odd">
<td><p>cmplMessage</p></td>
<td><p>nvarchar (max)</p></td>
<td><p>Message (le codage dépend de cmplType).</p></td>
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
<td><p>cmplEventID</p></td>
<td><p>Clé primaire.</p></td>
</tr>
</tbody>
</table>

