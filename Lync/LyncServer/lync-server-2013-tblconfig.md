---
title: 'Lync Server 2013 : tblConfig'
TOCTitle: tblConfig
ms:assetid: 7445e7db-c574-46fa-b964-8640d77047a8
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg558663(v=OCS.15)
ms:contentKeyID: 49297730
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblConfig dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

tblConfig contient des éléments de configuration non pris en charge du serveur de conversations permanentes, dans une seule ligne.

### Colonnes

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Colonne</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>configLabel</p></td>
<td><p>nvarchar (255), non null</p></td>
<td><p>Contient « pool ».</p></td>
</tr>
<tr class="even">
<td><p>configContent</p></td>
<td><p>nvarchar (max)</p></td>
<td><p>Contenu de configuration.</p></td>
</tr>
<tr class="odd">
<td><p>configPoolID</p></td>
<td><p>GUID, non null</p></td>
<td><p>ID unique de l’instance de base de données.</p></td>
</tr>
</tbody>
</table>


### Clé

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Colonne</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>configLabel</p></td>
<td><p>Clé primaire.</p></td>
</tr>
</tbody>
</table>

