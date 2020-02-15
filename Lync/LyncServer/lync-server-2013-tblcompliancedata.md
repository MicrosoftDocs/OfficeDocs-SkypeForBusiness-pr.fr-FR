---
title: 'Lync Server 2013 : tblComplianceData'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceData
ms:assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558606(v=OCS.15)
ms:contentKeyID: 48183308
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03f5a65b11c610849c5b9d031f24d236dcbcf332
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048505"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcompliancedata-in-lync-server-2013"></a>tblComplianceData dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-12_

tblComplianceData contient les événements de conformité qui n’ont pas encore été traités par l’ensemble des traducteurs inscrits.

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
<td><p>int, non null</p></td>
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
<td><p>URI (Uniform Resource Identifier) de canal.</p></td>
</tr>
<tr class="even">
<td><p>cmplChatID</p></td>
<td><p>comportant</p></td>
<td><p>ID de conversation (correspondant à la table tblChat.chatId).</p></td>
</tr>
<tr class="odd">
<td><p>cmplUserID</p></td>
<td><p>int, non null</p></td>
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
<td><p>cmplEventID</p></td>
<td><p>Clé primaire.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

