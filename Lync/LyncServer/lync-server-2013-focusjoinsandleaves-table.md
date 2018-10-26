---
title: 'Lync Server 2013 : Table FocusJoinsAndLeaves'
TOCTitle: Table FocusJoinsAndLeaves
ms:assetid: e6f0212c-67e9-4061-8720-d0296e855991
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg399026(v=OCS.15)
ms:contentKeyID: 49299166
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table FocusJoinsAndLeaves dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Chaque enregistrement de cette table contient les informations CDR sur l’arrivée et le départ d’un utilisateur dans une conférence. Chaque conférence est représentée dans cette table par un enregistrement pour chaque événement d’arrivée et de départ d’un utilisateur dans la conférence.


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
<td><p>datetime</p></td>
<td><p>Primaire, étrangère</p></td>
<td><p>Heure de l’instance de conférence. Utilisée de concert avec <strong>SessionIdSeq</strong> pour identifier de manière unique une instance de conférence. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-conferences-table.md">Table Conferences dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primaire, étrangère</p></td>
<td><p>Numéro d’identification de l’instance de conférence. Utilisée de concert avec <strong>SessionIdTime</strong> pour identifier de manière unique une instance de conférence. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-conferences-table.md">Table Conferences dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogSessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primaire, étrangère</p></td>
<td><p>Heure de la demande de session. Utilisée de concert avec <strong>SessionIdSeq</strong> pour identifier de manière unique une session. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-dialogs-table.md">Table Dialogs dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogSessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primaire, étrangère</p></td>
<td><p>Numéro d’identification de la session. Utilisée de concert avec <strong>SessionIdTime</strong> pour identifier de manière unique une session. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-dialogs-table.md">Table Dialogs dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>Étrangère</p></td>
<td><p>Numéro unique d’identification de cet utilisateur, référencé depuis la <a href="lync-server-2013-users-table.md">Table Users dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>FocusUserInstance</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Si un utilisateur est connecté sur plusieurs ordinateurs ou périphériques en même temps, la colonne <strong>UserInstance</strong> est utilisée pour identifier la combinaison utilisateur/périphérique.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsUserInternal</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Indique si l’utilisateur est connecté en interne ou non.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserRole</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Il s’agit du rôle de l’utilisateur dans la conférence, tel que présentateur ou participant.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserJoinTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>Heure à laquelle cet utilisateur rejoint la conférence.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserLeaveTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>Heure à laquelle cet utilisateur quitte la conférence.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientVerId</strong></p></td>
<td><p>int</p></td>
<td><p>Étrangère</p></td>
<td><p>Version du logiciel client de l’utilisateur, référencée dans la <a href="lync-server-2013-clientversions-table.md">Table ClientVersions dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserEndpointId</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td><p></p></td>
<td><p>Identificateur global unique (GUID) du point de terminaison utilisé dans la conférence.</p>
<p>Ce champ a été présenté dans Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>

