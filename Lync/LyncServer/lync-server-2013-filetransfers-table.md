---
title: 'Lync Server 2013 : Table FileTransfers'
TOCTitle: Table FileTransfers
ms:assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398353(v=OCS.15)
ms:contentKeyID: 49297257
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table FileTransfers dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Chaque enregistrement représente une session de transfert de fichiers.


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
<td><p>Heure de la demande de session. Utilisée de concert avec <strong>SessionIdSeq</strong> pour identifier de manière unique une session. Reportez-vous à la <a href="lync-server-2013-dialogs-table.md">Table Dialogs dans Lync Server 2013</a> pour plus d’informations.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>Int</p></td>
<td><p>Primaire, étrangère</p></td>
<td><p>Numéro d’ID identifiant la session. Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier de manière unique une session. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-dialogs-table.md">Table Dialogs dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>File Name</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p></p></td>
<td><p>Nom du fichier.</p></td>
</tr>
<tr class="even">
<td><p><strong>FileIdentity</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p></p></td>
<td><p>Identificateur unique permettant de différencier les transferts de fichiers concernant le même nom de fichier.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Cookie</strong></p></td>
<td><p>nvarchar(128)</p></td>
<td><p>Principal</p></td>
<td><p>Utilisé pour identifier chaque message de suivi comme étant associé à celui-ci.</p></td>
</tr>
<tr class="even">
<td><p><strong>Accept</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Peut-être TRUE ou NULL. Si TRUE, alors Reject et Cancel seront NULL.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Reject</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Peut-être TRUE ou NULL. Si TRUE, alors Accept et Cancel seront NULL.</p></td>
</tr>
<tr class="even">
<td><p><strong>Cancel</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Peut-être TRUE ou NULL. Si TRUE, alors Accept et Reject seront NULL.</p></td>
</tr>
</tbody>
</table>

