---
title: 'Lync Server 2013 : table McuJoinsAndLeaves'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: McuJoinsAndLeaves table
ms:assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398316(v=OCS.15)
ms:contentKeyID: 48184115
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 138fe5f989fb11986c3db6e134fa7f975a95c96e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149904"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-table-in-lync-server-2013"></a>Table McuJoinsAndLeaves dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-28_

Chaque enregistrement de cette table contient des détails sur une combinaison d’un utilisateur JOIN ou Leave et d’un serveur de conférence. Par exemple, si un utilisateur rejoint une conférence qui comprend des éléments audio/vidéo et de conférence Web, un enregistrement est créé pour la jointure de conférence Web de cet utilisateur, et un autre enregistrement est créé pour la jointure audio/vidéo de l’utilisateur.


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
<td><p>Heure de l’instance de conférence. Utilisé conjointement avec <strong>SessionIdSeq</strong> pour identifier une instance de conférence de manière unique. Pour plus d’informations, reportez-vous au <a href="lync-server-2013-conferences-table.md">tableau conférences de Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primaire, étrangère</p></td>
<td><p>Numéro d’identification de l’instance de conférence. Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier une instance de conférence de manière unique. Pour plus d’informations, reportez-vous au <a href="lync-server-2013-conferences-table.md">tableau conférences de Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>Primaire, étrangère</p></td>
<td><p>Numéro unique identifiant cet utilisateur. Pour plus d’informations, reportez-vous au <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>McuUserInstance</strong></p></td>
<td><p>int</p></td>
<td><p>Primaire</p></td>
<td><p>Si un utilisateur a ouvert une session sur plusieurs ordinateurs ou périphériques à la fois, McuUserInstance identifie de manière unique la combinaison utilisateur/périphérique.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsFromPstn</strong></p></td>
<td><p>légèrement</p></td>
<td><p> </p></td>
<td><p>Si l’utilisateur rejoint à partir d’un RTC ou non.</p></td>
</tr>
<tr class="even">
<td><p><strong>McuId</strong></p></td>
<td><p>int</p></td>
<td><p>Primaire, étrangère</p></td>
<td><p>Numéro unique identifiant ce serveur de conférence. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-mcus-table.md">table MCU de Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogSessionIdTime</strong></p></td>
<td><p>DateHeure</p></td>
<td><p>Etranger</p></td>
<td><p>Heure de la demande de session. Utilisée conjointement avec <strong>SessionIdSeq</strong> pour identifier de manière unique une session. Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogSessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger</p></td>
<td><p>Numéro d’ID pour identifier la session. Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier de manière unique une session. Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserJoinTime</strong></p></td>
<td><p>DateHeure</p></td>
<td><p> </p></td>
<td><p>Heure à laquelle cet utilisateur rejoint ce serveur de conférence.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserLeaveTime</strong></p></td>
<td><p>DateHeure</p></td>
<td><p> </p></td>
<td><p>Heure à laquelle cet utilisateur quitte ce serveur de conférence.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientVerId</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger</p></td>
<td><p>Identificateur qui spécifie le numéro de version de l’utilisation du logiciel client dans la Conférence. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-clientversions-table.md">table ClientVersions dans Lync Server 2013</a> .</p>
<p>Ce champ a été introduit dans Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

