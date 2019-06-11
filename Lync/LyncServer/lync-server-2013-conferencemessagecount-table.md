---
title: 'Lync Server 2013 : Table ConferenceMessageCount'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceMessageCount table
ms:assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398590(v=OCS.15)
ms:contentKeyID: 48184570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d2994f02bf087ef55edff6b2153e7504f881b03
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838483"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencemessagecount-table-in-lync-server-2013"></a>Table ConferenceMessageCount dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-28_

Chaque enregistrement de cette table représente un utilisateur au sein d’une conférence par messagerie instantanée et inclut le nombre de messages envoyés par cet utilisateur. Chaque conférence est représentée par plusieurs enregistrements dans ce tableau; un enregistrement pour chaque utilisateur.


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
<th>Clé/Index</th>
<th>Détails</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>DateHeure</p></td>
<td><p>Etranger principal</p></td>
<td><p>Durée de l’instance de conférence. Utilisé conjointement avec <strong>SessionIdSeq</strong> pour identifier de manière unique une instance de conférence. Pour plus d’informations, voir le <a href="lync-server-2013-conferences-table.md">tableau conférences dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger principal</p></td>
<td><p>Numéro d’identification pour identifier l’instance de conférence. Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier de manière unique une instance de conférence. Pour plus d’informations, voir le <a href="lync-server-2013-conferences-table.md">tableau conférences dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>Numéro unique identifiant cet utilisateur, référencé dans la <a href="lync-server-2013-users-table.md">table utilisateurs de Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>MessageCount</strong></p></td>
<td><p>type</p></td>
<td><p> </p></td>
<td><p>Nombre de messages envoyés par cet utilisateur au cours de cette conférence.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

