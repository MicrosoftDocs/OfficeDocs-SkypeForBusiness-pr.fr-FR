---
title: 'Lync Server 2013 : tblRoleType'
TOCTitle: tblRoleType
ms:assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg558623(v=OCS.15)
ms:contentKeyID: 49296466
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblRoleType dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

tblRoleType est une table de choix statique contenant des types de rôles et leurs jeux d’autorisations.

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
<td><p>rtypeID</p></td>
<td><p>entier, non null</p></td>
<td><p>ID de type de rôle.</p></td>
</tr>
<tr class="even">
<td><p>rtypeDesc</p></td>
<td><p>nvarchar (256), non null</p></td>
<td><p>Description de type de rôle. Les quatre rôles disponibles sont :</p>
<ul>
<li><p>Membre : membre de la salle de conversation</p></li>
<li><p>Responsable : responsable de la salle de conversation</p></li>
<li><p>Membre sonore : présentateur de la salle de conversation de type auditorium</p></li>
<li><p>Créateur : peut créer des salles de conversation</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>rtypeAllowedPermSet</p></td>
<td><p>bigint, non null</p></td>
<td><p>Définition de l’autorisation du rôle. Les bits utilisés sont :</p>
<ul>
<li><p>2 : True si le rôle peut gérer des nœuds.</p></li>
<li><p>4 : True si le rôle peut créer des nœuds enfants.</p></li>
<li><p>7 : True si le rôle peut rejoindre une salle de conversation (ou les salles de conversation enfants d’une catégorie).</p></li>
<li><p>8 : True si le rôle peut converser dans une salle de conversation (ou les salles de conversation enfants d’une catégorie).</p></li>
<li><p>10 : True si le rôle peut lire l’historique d’une conversation même s’il n’a pas rejoint une salle de conversation.</p></li>
<li><p>11 : True si le rôle peut voir la salle de conversation. (Les facteurs tels que l’étendue et la visibilité permettent d’affiner davantage).</p></li>
<li><p>12 : True si le rôle peut converser dans la salle de conversation de type auditorium.</p></li>
<li><p>13 : True si le rôle peut contourner les règles de visibilité lors de la visualisation des nœuds.</p></li>
</ul></td>
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
<td><p>rtypeID</p></td>
<td><p>Clé primaire.</p></td>
</tr>
</tbody>
</table>

