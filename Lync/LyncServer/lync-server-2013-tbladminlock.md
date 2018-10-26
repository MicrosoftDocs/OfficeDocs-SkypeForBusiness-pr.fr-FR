---
title: 'Lync Server 2013 : tblAdminLock'
TOCTitle: tblAdminLock
ms:assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg558665(v=OCS.15)
ms:contentKeyID: 49297802
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblAdminLock dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

tblAdminLock contient le verrou d’administrateur nécessaire pour exécuter certaines commandes d’administration.

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
<td><p>lockExpiresTime</p></td>
<td><p>datetime, non null</p></td>
<td><p>Date et heure d’expiration du verrou. Le propriétaire peut étendre cette valeur de manière périodique.</p></td>
</tr>
<tr class="even">
<td><p>lockServerID</p></td>
<td><p>entier, non null</p></td>
<td><p>ID du serveur qui détient le verrou.</p></td>
</tr>
<tr class="odd">
<td><p>lockActorID</p></td>
<td><p>entier, non null</p></td>
<td><p>ID du principal qui détient le verrou.</p></td>
</tr>
</tbody>
</table>

