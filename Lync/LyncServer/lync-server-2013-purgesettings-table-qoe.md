---
title: Table PurgeSettings (QoE) dans Lync Server 2013
TOCTitle: Table PurgeSettings (QoE) dans Lync Server 2013
ms:assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204788(v=OCS.15)
ms:contentKeyID: 49296783
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table PurgeSettings (QoE) dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La table PurgeSettings contient des informations indiquant si (et quand) les enregistrements de qualité de l’expérience obsolètes doivent être automatiquement supprimés de la base de données QoE. Notez que les informations relatives au vidage peuvent aussi être obtenues dans Microsoft Lync Server 2013 Management Shell à l’aide de la commande suivante :

    Get-CsQoEConfiguration

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
<th><strong>Colonne</strong></th>
<th><strong>Type de données</strong></th>
<th><strong>Clé/Index</strong></th>
<th><strong>Détails</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ID</strong></p></td>
<td><p>int</p></td>
<td><p>Principal</p></td>
<td><p>Identificateur unique pour la collecte des paramètres de vidage QoE.</p></td>
</tr>
<tr class="even">
<td><p><strong>EnablePurge</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Si la valeur est True (1), Microsoft Lync Server 2013 vide périodiquement la base de données QoE des enregistrements obsolètes. Le vidage s’effectue chaque jour au niveau du tome spécifié par le paramètre PurgeHour. Si la valeur est False (0), les enregistrements ne sont pas supprimés automatiquement de la base de données. La valeur par défaut est True.</p></td>
</tr>
<tr class="odd">
<td><p><strong>KeepQoEDataForDays</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Spécifie l’âge des enregistrements QoE (en jours) qui seront supprimés de la base de données : si le vidage est activé, les enregistrements QoE antérieurs à cette valeur seront supprimés de la base de données. La valeur par défaut est 60 jours.</p></td>
</tr>
<tr class="even">
<td><p><strong>PurgeHour</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Spécifie l’heure locale du jour auquel le vidage a lieu. L’heure du jour est indiquée au format 24 heures, 0 représentant minuit (12:00 AM) et 23 représentant 11:00 PM. Notez que vous ne pouvez spécifier que des heures : la valeur 10 (10:00 AM) est autorisée, mais la valeur 10,5 (10:30 AM) n’est pas autorisée. La valeur par défaut est 1 (1:00 AM). Spécifie l’heure locale du jour auquel le vidage a lieu. L’heure du jour est indiquée au format 24 heures, 0 représentant minuit (12:00 AM) et 23 représentant 11:00 PM. Notez que vous ne pouvez spécifier que des heures : la valeur 10 (10:00 AM) est autorisée, mais la valeur 10,5 (10:30 AM) n’est pas autorisée. La valeur par défaut est 1 (1:00 AM).</p></td>
</tr>
</tbody>
</table>

