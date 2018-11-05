---
title: Table NetworkConnectionDetail dans Lync Server 2013
TOCTitle: Table NetworkConnectionDetail dans Lync Server 2013
ms:assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205185(v=OCS.15)
ms:contentKeyID: 49298581
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table NetworkConnectionDetail dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La table NetworkConnectionDetail mappe des types de connexion réseau aux identificateurs de connexion réseau utilisés ailleurs dans la base de données Qualité de l’expérience (QoE). Cette table est une nouveauté de Microsoft Lync Server 2013.


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
<td><p><strong>NetworkConnectionDetailKey</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primaire</p></td>
<td><p>Identificateur unique du type de connexion réseau.</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkConnectionDetail</strong></p></td>
<td><p>varchar(256)</p></td>
<td><p>Unique</p></td>
<td><p>Type de connexion réseau correspondant à la valeur NetworkConnectionDetailKey. Les valeurs autorisées sont les suivantes :</p>
<ol>
<li><p>0 -- Câblé</p></li>
<li><p>1 -- WiFi</p></li>
<li><p>2 -- Ethernet</p></li>
</ol></td>
</tr>
</tbody>
</table>

