---
title: Table UserStatistics dans Lync Server 2013
TOCTitle: Table UserStatistics dans Lync Server 2013
ms:assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721893(v=OCS.15)
ms:contentKeyID: 49891552
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table UserStatistics dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La table UserStatistics est une table de prise en charge. Chaque enregistrement dans la table stocke les informations sur l’utilisation individuelle d’un utilisateur du système. Cette table est une nouveauté de Microsoft Lync Server 2013.


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
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>Principal</p></td>
<td><p>Numéro unique identifiant cet utilisateur.</p></td>
</tr>
<tr class="even">
<td><p><strong>LastLogInTime</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>Heure de la dernière connexion de l’utilisateur.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LastConfOrganizedTime</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>Heure de la dernière organisation d’une conférence par l’utilisateur.</p></td>
</tr>
<tr class="even">
<td><p><strong>LastCallOrganizerCallFailureTime</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>Heure du dernier échec d’appel de l’utilisateur.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LastConfOrganizerCallFailureTime</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>Heure du dernier échec d’appel de l’utilisateur en tant qu’organisateur de conférence.</p></td>
</tr>
</tbody>
</table>

