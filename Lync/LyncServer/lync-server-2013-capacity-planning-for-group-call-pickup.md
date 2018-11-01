---
title: Planification de la capacité pour la prise d’appel de groupe
TOCTitle: Planification de la capacité pour la prise d’appel de groupe
ms:assetid: 0d654a19-6cf0-4118-903d-ec2c4e519253
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ984297(v=OCS.15)
ms:contentKeyID: 53095356
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planification de la capacité pour la prise d’appel de groupe

 

_**Dernière rubrique modifiée :** 2015-03-09_

Le tableau suivant décrit le modèle utilisateur de la prise d’appel de groupe dont vous pouvez vous servir comme base pour les exigences de planification de capacité.

> [!IMPORTANT]  
> La prise d’appel de groupe repose sur l’application de parcage d’appel. N’oubliez pas que, pour la planification de la capacité de récupération d’urgence, chaque pool associé à un autre pool doit être en mesure de gérer les charges de travail des services de parcage d’appel, y compris la prise d’appel de groupe, dans les deux pools.

### Modèle utilisateur de la prise d’appel de groupe

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Mesure</th>
<th>Par pool de serveurs frontaux (avec 8 serveurs frontaux)</th>
<th>Par serveur Standard Edition</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nombre recommandé d’utilisateurs par groupe</p></td>
<td><p>50</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>Nombre recommandé de groupes</p></td>
<td><p>500</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>Nombre maximum d’utilisateurs par pool autorisé pour la prise d’appel de groupe</p></td>
<td><p>25 000</p></td>
<td><p>3 000</p></td>
</tr>
<tr class="even">
<td><p>Rapport maximal entre le nombre d’appels entrants et le nombre total d’utilisateurs autorisé pour la prise d’appel de groupe par pool et par minute</p></td>
<td><p>500</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>Taux maximal d’appels récupérés par les utilisateurs avec la prise d’appel de groupe par pool et par minute</p></td>
<td><p>200</p></td>
<td><p>25</p></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> <ul>
> <li><p>Pour les pools de serveurs frontaux possédant moins de huit serveurs frontaux, calculez les mesures de manière linéaire. Par exemple, si votre pool de serveurs frontaux possède un serveur frontal, divisez par 8 les valeurs indiquées dans le tableau pour calculer la charge maximale.</p></li>
> <li><p>Vous pouvez augmenter ou diminuer le nombre d’utilisateurs par groupe et le nombre de groupes recommandés tant que vous ne dépassez pas le nombre d’utilisateurs maximal par pool. Par exemple, votre serveur Standard Edition peut compter 120 groupes de 25 utilisateurs, car le nombre d’utilisateurs autorisés pour la prise d’appel de groupe respecte les valeurs maximales du modèle utilisateur (en d’autres termes, 120 groupes de 25 utilisateurs représentent 3 000 utilisateurs autorisés pour la prise d’appel de groupe).</p></li></ul>

