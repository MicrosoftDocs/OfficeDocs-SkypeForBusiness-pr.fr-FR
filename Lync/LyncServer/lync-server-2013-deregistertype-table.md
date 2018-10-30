---
title: 'Lync Server 2013 : Table DeRegisterType'
TOCTitle: Table DeRegisterType
ms:assetid: 09148118-6209-4fd7-a494-99118689a245
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398142(v=OCS.15)
ms:contentKeyID: 49296182
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table DeRegisterType dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La table DeRegisterType est une table statique qui stocke la liste des différents types de désinscriptions liées aux utilisateurs, tels que « initiative du client », « expiration de l’inscription » ou « absence de réponse du client ».


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
<td><p><strong>DeRegisterTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Principal</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>DeRegisterReason</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p></p></td>
<td><p>Valeurs autorisées :</p>
<ul>
<li><p>0 - Inconnu</p></li>
<li><p>1 - Désinscription à l’initiative du client</p></li>
<li><p>2 - Expiration de l’inscription</p></li>
<li><p>3 - Client bloqué</p></li>
<li><p>4 - Modification des attributs de l’utilisateur</p></li>
<li><p>5 - Modification du serveur d’inscriptions préféré</p></li>
<li><p>6 - Client hérité en mode survie</p></li>
</ul></td>
</tr>
</tbody>
</table>

