---
title: Vue UserAgent
TOCTitle: Vue UserAgent
ms:assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721862(v=OCS.15)
ms:contentKeyID: 49891509
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vue UserAgent

 

_**Dernière rubrique modifiée :** 2015-03-09_

L’affichage UserAgent stocke les informations relatives aux agents utilisateur qui ont été impliqués dans des sessions ayant des enregistrements dans la base de données. Cette vue est une nouveauté de Microsoft Lync Server 2013.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Colonne</th>
<th>Type de données</th>
<th>Détails</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UserAgentKey</p></td>
<td><p>int</p></td>
<td><p>Numéro unique qui identifie cet agent utilisateur.</p></td>
</tr>
<tr class="even">
<td><p>UserAgent</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Chaîne d’agent utilisateur.</p></td>
</tr>
<tr class="odd">
<td><p>UAType</p></td>
<td><p>smallint</p></td>
<td><p>Type d’agent utilisateur. Pour plus d’informations, voir <a href="lync-server-2013-useragent-table.md">Table UserAgent dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>UACategory</p></td>
<td><p>nvarchar(64)</p></td>
<td><p>Catégorie à laquelle appartient l’agent utilisateur. Par exemple, l’agent utilisateur Conferencing_Attendant_1.0 appartient au standard automatique de conférence (CAA) UACategory.</p></td>
</tr>
</tbody>
</table>

