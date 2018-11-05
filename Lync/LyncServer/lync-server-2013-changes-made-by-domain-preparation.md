---
title: Modifications effectuées par la préparation de domaine dans Lync Server 2013
TOCTitle: Modifications effectuées par la préparation de domaine dans Lync Server 2013
ms:assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398742(v=OCS.15)
ms:contentKeyID: 49298085
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Modifications effectuées par la préparation de domaine dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Le tableau ci-après répertorie les entrées de contrôle d’accès créées par la préparation de domaine sur la racine de domaine. Toutes les entrées de contrôle d’accès sont héritées, sauf indication contraire.

### Entrées de contrôle d’accès ajoutées à la racine de domaine

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>Entrée de contrôle d’accès</th>
<th>RTCUniversal-UserReadOnly-Group</th>
<th>RTCUniversal-ServerReadOnly-Group</th>
<th>RTCUniversal-UserAdmins</th>
<th>RTCHSUniversal-Services</th>
<th>Authenticated-Users</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Read Container (non héritée)</p></td>
<td><p><strong>Oui</strong></p></td>
<td><p><strong>Oui</strong></p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
</tr>
<tr class="even">
<td><p>Read User PropertySet User-Account-Restrictions</p></td>
<td><p><strong>Oui</strong></p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
</tr>
<tr class="odd">
<td><p>Read User PropertySet Personal-Information</p></td>
<td><p><strong>Oui</strong></p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
</tr>
<tr class="even">
<td><p>Read User PropertySet General-Information</p></td>
<td><p><strong>Oui</strong></p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
</tr>
<tr class="odd">
<td><p>Read User PropertySet Public-Information</p></td>
<td><p><strong>Oui</strong></p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
</tr>
<tr class="even">
<td><p>Read User PropertySet RTCUserSearchProperty-Set</p></td>
<td><p><strong>Oui</strong></p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p><strong>Oui</strong></p></td>
</tr>
<tr class="odd">
<td><p>Read User PropertySet RTCPropertySet</p></td>
<td><p><strong>Oui</strong></p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
</tr>
<tr class="even">
<td><p>Write User Property Proxy-Addresses</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p><strong>Oui</strong></p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
</tr>
<tr class="odd">
<td><p>Write User PropertySet RTCUserSearchProperty-Set</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p><strong>Oui</strong></p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
</tr>
<tr class="even">
<td><p>Write User PropertySet RTCPropertySet</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p><strong>Oui</strong></p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
</tr>
<tr class="odd">
<td><p>Read PropertySet DS-Replication-Get-Changes de tous les objets Active Directory</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p><strong>Oui</strong></p></td>
<td><p>Non</p></td>
</tr>
</tbody>
</table>


Le tableau suivant répertorie les entrées de contrôle d’accès créées par la préparation de domaine dans les trois conteneurs intégrés : Utilisateurs, Ordinateurs et Contrôleurs de domaine. Toutes les entrées de contrôle d’accès sont héritées, sauf indication contraire.

### Entrées de contrôle d’accès ajoutées aux conteneurs intégrés

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Entrée de contrôle d’accès</th>
<th>RTCUniversal-UserReadOnly-Group</th>
<th>RTCUniversal-ServerReadOnly-Group</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Read Container (non héritée)</p></td>
<td><p><strong>Oui</strong></p></td>
<td><p><strong>Oui</strong></p></td>
</tr>
</tbody>
</table>

