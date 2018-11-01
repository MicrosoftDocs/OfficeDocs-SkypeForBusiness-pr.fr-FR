---
title: 'Lync Server 2013 : Table PayloadDescription'
TOCTitle: Table PayloadDescription
ms:assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412971(v=OCS.15)
ms:contentKeyID: 49298794
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table PayloadDescription dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La table PayloadDescription est une table de prise en charge. Chaque enregistrement représente un codec utilisé dans une session audio ou vidéo.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Colonne</strong></th>
<th><strong>Type de données</strong></th>
<th><strong>Clé/Index</strong></th>
<th><strong>Détails</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>PayloadDescriptionKey</strong></p></td>
<td><p>int</p></td>
<td><p>Principal</p></td>
<td><p>Numéro unique identifiant le codec.</p></td>
</tr>
<tr class="even">
<td><p><strong>PayloadDescription</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Unique</p></td>
<td><p>Nom du codec.</p></td>
</tr>
</tbody>
</table>

