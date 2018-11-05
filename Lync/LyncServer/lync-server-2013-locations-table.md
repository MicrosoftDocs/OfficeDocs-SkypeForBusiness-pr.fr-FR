---
title: 'Lync Server 2013 : Table Locations'
TOCTitle: Table Locations
ms:assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398596(v=OCS.15)
ms:contentKeyID: 49297790
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table Locations dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Chaque enregistrement représente une référence d’emplacement dans un appel d’urgence, par exemple, un appel E9-1-1.


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
<td><p>Heure de la demande de session. Utilisée de concert avec <strong>SessionIdSeq</strong> pour identifier de manière unique une session. reportez-vous à la <a href="lync-server-2013-dialogs-table.md">Table Dialogs dans Lync Server 2013</a> pour plus d’informations.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primaire, étrangère</p></td>
<td><p>Numéro d’ID identifiant la session. Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier de manière unique une session. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-dialogs-table.md">Table Dialogs dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Emplacement</strong></p></td>
<td><p>nvarchar (max)</p></td>
<td><p></p></td>
<td><p>Emplacement de l’appel d’urgence.</p></td>
</tr>
</tbody>
</table>

