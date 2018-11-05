---
title: 'Lync Server 2013 : Table MediaList'
TOCTitle: Table MediaList
ms:assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398279(v=OCS.15)
ms:contentKeyID: 49296469
ms.date: 07/12/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table MediaList dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-07-12_

La table MediaList est une table statique qui stocke la liste de divers types de médias.


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
<td><p><strong>MediaId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Principal</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>Media</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p></p></td>
<td><p>Valeurs autorisées :</p>
<ul>
<li><p>1 – Messagerie instantanée</p></li>
<li><p>2 – Transfert de fichiers</p></li>
<li><p>3 – Assistance à distance</p></li>
<li><p>4 – Partage d’application</p></li>
<li><p>5 – Audio</p></li>
<li><p>6 – Vidéo</p></li>
<li><p>7 – Invitation d’application</p></li>
</ul></td>
</tr>
</tbody>
</table>

