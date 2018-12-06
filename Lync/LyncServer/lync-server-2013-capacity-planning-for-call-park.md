---
title: 'Lync Server 2013 : Planification de capacité pour le parcage d’appel'
TOCTitle: Planification de capacité pour le parcage d’appel
ms:assetid: 75520310-760a-4b1b-bcc1-4d724d13f87a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg416493(v=OCS.15)
ms:contentKeyID: 49297764
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planification de capacité pour le parcage d’appel dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Le tableau ci-dessous décrit le modèle utilisateur de parcage d’appel dont vous pouvez vous servir comme base pour les exigences de planification de capacité.

> [!IMPORTANT]  
> N’oubliez pas que, pour la planification de la capacité de récupération d’urgence, chaque pool associé à un autre pool doit être en mesure de gérer les charges de travail des services de parcage d’appel dans les deux pools.

### Modèle utilisateur de parcage d’appel

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
<th>Per serveur Standard Edition</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Taux de parcage</p></td>
<td><p>8 par minute</p></td>
<td><p>1 par minute</p></td>
</tr>
<tr class="even">
<td><p>Taux d’appels parqués récupérés</p></td>
<td><p>8 par minute</p></td>
<td><p>1 par minute</p></td>
</tr>
<tr class="odd">
<td><p>Durée moyenne de parcage</p></td>
<td><p>60 secondes</p></td>
<td><p>60 secondes</p></td>
</tr>
</tbody>
</table>

