---
title: "Lync Server 2013 : Liste tables de confor. avec le serv. de conversation perm."
TOCTitle: Liste des tables de conformité avec le serveur de conversation permanente
ms:assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ215878(v=OCS.15)
ms:contentKeyID: 49297945
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Liste des tables de conformité avec le serveur de conversation permanente dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Le schéma de base de données de conformité de conversation permanente comprend les tables suivantes.

## Liste des tables de conformité du serveur de conversations permanentes


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData dans Lync Server 2013</a></p></td>
<td><p>Contient les événements de conformité qui n’ont pas encore été traités par la carte configurée.</p>
<p>Cette table inclut des événements liés aux conversation permanente, tels que des messages de conversations et des téléchargements de fichiers. (Les événements des participants sont suivis par la table tblComplianceParticipant.)</p>
<p>(Les serveurs qui ont traité les événements de cette table sont répertoriés dans la table tblComplianceFanout.)</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout dans Lync Server 2013</a></p></td>
<td><p>Contient les serveurs qui ont traité un événement de conformité. Celle-ci est étroitement associée à la table tblComplianceData.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant dans Lync Server 2013</a></p></td>
<td><p>Contient les participants actifs par service de conversation et par serveur. Elle est mise à jour en fonction des événements de conformité de participation et de départ reçus du service de conversation permanente.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState dans Lync Server 2013</a></p></td>
<td><p>Contient les informations d’état de conformité au niveau du pool.</p></td>
</tr>
</tbody>
</table>

