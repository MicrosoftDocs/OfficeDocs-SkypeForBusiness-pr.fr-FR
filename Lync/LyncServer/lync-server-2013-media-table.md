---
title: 'Lync Server 2013 : table Media'
description: 'Lync Server 2013 : tableau multimédia.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media table
ms:assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398268(v=OCS.15)
ms:contentKeyID: 48183568
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31e30d1f91c59b8e3aa7915fc0d513618d0f709f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558030"
---
# <a name="media-table-in-lync-server-2013"></a>Table Media dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-28_

Chaque enregistrement représente un type de média utilisé au cours d’une session d’égal à égal. Une session est représentée par plusieurs enregistrements dans la table, si plusieurs types de médias sont utilisés.

<div>


> [!NOTE]  
> La table Media ne doit pas être utilisée pour calculer la durée du média lors d’une session. Cette table contient les détails de signalisation de l’échange multimédia lors d’une session. L’échange multimédia est effectué par la requête INVITE et StartTime indique l’heure à laquelle la requête INVITE a été envoyée. L’heure d’invitation ne signifie pas nécessairement l’heure de début du média, car le média démarre seulement lorsque le destinataire de la session accepte la session. EndTime signifie généralement l’heure de fin de cette session.



</div>


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
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>DateHeure</p></td>
<td><p>Primaire, étrangère</p></td>
<td><p>Heure de la demande de session. Utilisée conjointement avec <strong>SessionIdSeq</strong> pour identifier de manière unique une session. Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primaire, étrangère</p></td>
<td><p>Numéro d’ID pour identifier la session. Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier de manière unique une session. Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaId</strong></p></td>
<td><p>entier très petit</p></td>
<td><p>Primaire, étrangère</p></td>
<td><p>Numéro unique d’identification de ce type de média. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-medialist-table.md">table médial dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>StartTime</strong></p></td>
<td><p>DateHeure</p></td>
<td><p>Primaire</p></td>
<td><p>Heure d’envoi de la demande multimédia, et non pas heure réelle du début du média. <strong>StartTime</strong> inclut l’heure de configuration de la session.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndTime</strong></p></td>
<td><p>DateHeure</p></td>
<td></td>
<td><p>Heure de fin de la session.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

