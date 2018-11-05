---
title: 'Lync Server 2013 : Table ClientVersions'
TOCTitle: Table ClientVersions
ms:assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398356(v=OCS.15)
ms:contentKeyID: 49297264
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table ClientVersions dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La table ClientVersions est une table de prise en charge qui stocke la liste des divers types et versions de clients ayant participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente une version de client.


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
<td><p><strong>VersionId</strong></p></td>
<td><p><strong>int</strong></p></td>
<td><p>Principal</p></td>
<td><p>Numéro unique identifiant le type et la version de ce client.</p></td>
</tr>
<tr class="even">
<td><p><strong>Version</strong></p></td>
<td><p><strong>nvarchar(256)</strong></p></td>
<td><p></p></td>
<td><p>Nom de la version.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientType</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Spécifie le type de client utilisé dans la session. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-useragentdef-table.md">Table UserAgentDef dans Lync Server 2013</a>.</p>
<p>Ce champ a été présenté dans Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>

