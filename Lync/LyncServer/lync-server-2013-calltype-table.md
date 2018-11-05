---
title: 'Lync Server 2013 : Table CallType'
TOCTitle: Table CallType
ms:assetid: a1d7187c-f851-4967-88ea-73922911ee7a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412752(v=OCS.15)
ms:contentKeyID: 49298406
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table CallType dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La table CallType est une table statique qui contient la liste de types d’appels possibles.


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
<td><p><strong>CallTypeId</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>CallType</strong></p></td>
<td><p>nvarchar</p></td>
<td><p></p></td>
<td><p>Valeurs autorisées :</p>
<ul>
<li><p>0 - Inconnu</p></li>
<li><p>1 - Messagerie instantanée</p></li>
<li><p>2 - Partage d’application</p></li>
<li><p>3 – Audio</p></li>
<li><p>4 - Audio et vidéo</p></li>
<li><p>5 - Transfert de fichiers</p></li>
</ul></td>
</tr>
</tbody>
</table>

