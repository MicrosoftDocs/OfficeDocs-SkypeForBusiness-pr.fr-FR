---
title: Table PurgeSettings dans Lync Server 2013
TOCTitle: Table PurgeSettings dans Lync Server 2013
ms:assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205121(v=OCS.15)
ms:contentKeyID: 49298347
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table PurgeSettings dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La table PurgeSettings contient des informations qui indiquent si (et quand) les enregistrements des détails des appels obsolètes sont supprimés automatiquement de la base de données d’enregistrement des détails des appels. Notez que les informations relatives à la suppression peuvent également être obtenues à partir de Microsoft Lync Server 2013 Management Shell en exécutant la commande suivante :

    Get-CsCdrConfiguration

Les administrateurs doivent traiter la table PurgeSettings comme étant en lecture seule : toute modification des paramètres de suppression de détails des appels doit être effectuée uniquement à l’aide de l’applet de commande [New-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsCdrConfiguration) ou [Set-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCdrConfiguration).

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
<td><p><strong>Id</strong></p></td>
<td><p>entier</p></td>
<td><p>Principal</p></td>
<td><p>Identificateur unique de la collection des paramètres de suppression des enregistrements des détails des appels.</p></td>
</tr>
<tr class="even">
<td><p><strong>EnablePurge</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Si la valeur est True (1), Microsoft Lync Server 2013 supprime périodiquement les enregistrements obsolètes de la base de données d’enregistrement des détails des appels. LA suppression a lieu tous les jours à l’heure indiquée par le paramètre PurgeHour. Si la valeur est False (0), les enregistrements ne sont pas supprimés automatiquement de la base de données. La valeur par défaut est True.</p></td>
</tr>
<tr class="odd">
<td><p><strong>KeepCallDetailForDays</strong></p></td>
<td><p>entier</p></td>
<td><p></p></td>
<td><p>Indique l’âge des enregistrements des détails des appels (en jours) qui seront supprimés de la base de données : si la suppression est activée, les enregistrements des détails des appels dont l’antériorité est supérieure à cette valeur seront supprimés de la base de données. La valeur par défaut est 60 jours.</p></td>
</tr>
<tr class="even">
<td><p><strong>KeepErrorReportForDays</strong></p></td>
<td><p>entier</p></td>
<td><p></p></td>
<td><p>Indique l’âge des enregistrements de rapport d’erreurs (en jours) qui seront supprimés de la base de données : si la suppression est activée, les enregistrements de rapport d’erreurs dont l’antériorité est supérieure à cette valeur seront supprimés de la base de données. La valeur par défaut est 60 jours.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PurgeHour</strong></p></td>
<td><p>entier</p></td>
<td><p></p></td>
<td><p>Indique l’heure locale de la journée à laquelle la suppression de la base de données a lieu. L’heure de la journée est spécifiée à l’aide de l’horloge 24 heures, avec 0 qui représente minuit (00h00) et 23 qui représente 23h00. Notez que vous ne pouvez spécifier que l’heure de la journée : la valeur 10 (indiquant 10h00) est autorisée, mais la valeur 10,5 (indiquant 10h30) est interdite. La valeur par défaut est 2 (02h00).</p></td>
</tr>
</tbody>
</table>

