---
title: 'Lync Server 2013 : tblComplianceState'
TOCTitle: tblComplianceState
ms:assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg615045(v=OCS.15)
ms:contentKeyID: 49299209
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblComplianceState dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

tblComplianceState contient des informations d’état de conformité à l’échelle du pool.

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
<td><p>lastProcessedEntryID</p></td>
<td><p>bigint, non null</p></td>
<td><p>ID du dernier événement de conformité traité.</p></td>
</tr>
<tr class="even">
<td><p>activeServerID</p></td>
<td><p>entier, non null</p></td>
<td><p>ID du serveur de conformité verrouillant de manière exclusive la base de données, ou -1 s’il n’existe pas.</p></td>
</tr>
<tr class="odd">
<td><p>lockExpirationTime</p></td>
<td><p>dateheure2, non null</p></td>
<td><p>Heure d’expiration du verrou (si activeServerID est différent de -1).</p></td>
</tr>
</tbody>
</table>

