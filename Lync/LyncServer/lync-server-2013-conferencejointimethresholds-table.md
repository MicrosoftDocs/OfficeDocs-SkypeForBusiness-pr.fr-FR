---
title: Table ConferenceJoinTimeThresholds dans Lync Server 2013
TOCTitle: Table ConferenceJoinTimeThresholds dans Lync Server 2013
ms:assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204809(v=OCS.15)
ms:contentKeyID: 49296919
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table ConferenceJoinTimeThresholds dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La table ConferenceJoinTimeThresholds contient les limites de classification utilisées par le rapport de synthèse du temps de connexion à la conférence. Ce rapport récapitule le temps nécessaire aux utilisateurs pour se joindre à une conférence. Ces valeurs de temps représentent à la fois une moyenne et l’une des catégories suivantes :

  - Moins de 2 secondes.

  - Entre 2 et 5 secondes.

  - Entre 5 et 10 secondes.

  - Plus de 10 secondes.

La table ConferenceJoinTimeThresholds contient les valeurs de classification 2 secondes, 5 secondes et 10 secondes.

Cette table est une nouveauté de Microsoft Lync Server 2013.


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
<td><p><strong>Seuil</strong></p></td>
<td><p>int</p></td>
<td><p>Primaire</p></td>
<td><p>Identificateur unique de la classification.</p></td>
</tr>
<tr class="even">
<td><p><strong>ThresholdValue</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Limite supérieure de la classification. Les valeurs autorisées sont les suivantes :</p>
<ol>
<li><p>2</p></li>
<li><p>5</p></li>
<li><p>10</p></li>
</ol></td>
</tr>
</tbody>
</table>

