---
title: 'Lync Server 2013 : Table McuJoinsAndLeaves'
TOCTitle: Table McuJoinsAndLeaves
ms:assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398316(v=OCS.15)
ms:contentKeyID: 49297165
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table McuJoinsAndLeaves dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Chaque enregistrement de cette table contient les détails des appels sur la participation ou l’arrêt de la participation d’un utilisateur à une conférence, ainsi que sur le serveur de conférence concerné. Par exemple, si un utilisateur participe à une conférence qui inclut une conférence web et des éléments audio/vidéo, un enregistrement est créé pour la participation de cet utilisateur à la conférence web, tandis qu’un autre enregistrement est créé pour la participation de l’utilisateur à la conférence audio/vidéo.


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
<td><p>Heure de l’instance de conférence. Utilisée de concert avec <strong>SessionIdSeq</strong> pour identifier de manière unique une instance de conférence. Reportez-vous à la <a href="lync-server-2013-conferences-table.md">Table Conferences dans Lync Server 2013</a> pour plus d’informations.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>Int</p></td>
<td><p>Primaire, étrangère</p></td>
<td><p>Numéro d’identification de l’instance de conférence. Utilisée de concert avec <strong>SessionIdTime</strong> pour identifier de manière unique une instance de conférence. Reportez-vous à la <a href="lync-server-2013-conferences-table.md">Table Conferences dans Lync Server 2013</a> pour plus d’informations.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserId</strong></p></td>
<td><p>Int</p></td>
<td><p>Primaire, étrangère</p></td>
<td><p>Numéro unique identifiant cet utilisateur. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-users-table.md">Table Users dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>McuUserInstance</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Si un utilisateur est connecté à plusieurs ordinateurs ou périphériques à la fois, McuUserInstance identifie de manière unique la combinaison utilisateur/périphérique.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsFromPstn</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Si l’utilisateur provient d’un réseau téléphonique commuté (RTC) ou non.</p></td>
</tr>
<tr class="even">
<td><p><strong>McuId</strong></p></td>
<td><p>Int</p></td>
<td><p>Primaire, étrangère</p></td>
<td><p>Numéro unique identifiant ce serveur de conférence. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-mcus-table.md">Table Mcus dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogSessionIdTime</strong></p></td>
<td><p>DateHeure</p></td>
<td><p>Étrangère</p></td>
<td><p>Heure de la demande de session. Utilisée de concert avec <strong>SessionIdSeq</strong> pour identifier de manière unique une session. Reportez-vous à la <a href="lync-server-2013-dialogs-table.md">Table Dialogs dans Lync Server 2013</a> pour plus d’informations.</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogSessionIdSeq</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Numéro d’ID identifiant la session. Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier de manière unique une session. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-dialogs-table.md">Table Dialogs dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserJoinTime</strong></p></td>
<td><p>DateHeure</p></td>
<td><p> </p></td>
<td><p>Heure à laquelle cet utilisateur se joint à ce serveur de conférence.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserLeaveTime</strong></p></td>
<td><p>DateHeure</p></td>
<td><p> </p></td>
<td><p>Heure à laquelle cet utilisateur quitte ce serveur de conférence.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientVerId</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Identificateur qui spécifie le numéro de version du logiciel client utilisé dans cette conférence. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-clientversions-table.md">Table ClientVersions dans Lync Server 2013</a>.</p>
<p>Ce champ a été présenté dans Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>

