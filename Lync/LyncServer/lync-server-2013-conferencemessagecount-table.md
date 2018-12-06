---
title: 'Lync Server 2013 : Table ConferenceMessageCount'
TOCTitle: Table ConferenceMessageCount
ms:assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398590(v=OCS.15)
ms:contentKeyID: 49297801
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table ConferenceMessageCount dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Chaque enregistrement de cette table représente un utilisateur dans une conférence de messagerie instantanée et inclut le nombre de messages envoyés par cet utilisateur. Chaque conférence est représentée par plusieurs enregistrements dans cette table, un enregistrement correspondant à un utilisateur.


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
<td><p>Primaire, étrangère</p></td>
<td><p>Heure de l’instance de conférence. Utilisée de concert avec <strong>SessionIdSeq</strong> pour identifier de manière unique une instance de conférence. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-conferences-table.md">Table Conferences dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>Int</p></td>
<td><p>Primaire, étrangère</p></td>
<td><p>Numéro d’identification de l’instance de conférence. Utilisée de concert avec <strong>SessionIdTime</strong> pour identifier de manière unique une instance de conférence. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-conferences-table.md">Table Conferences dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserId</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Numéro unique d’identification de cet utilisateur, référencé depuis la <a href="lync-server-2013-users-table.md">Table Users dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>MessageCount</strong></p></td>
<td><p>smallint</p></td>
<td><p> </p></td>
<td><p>Nombre de messages envoyés par cet utilisateur durant cette conférence.</p></td>
</tr>
</tbody>
</table>

