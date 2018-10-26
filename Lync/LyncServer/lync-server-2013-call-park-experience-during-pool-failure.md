---
title: "Lync Server 2013 : Exp. de parcage d’appel en cas de défaillance d’un pool"
TOCTitle: Expérience de parcage d’appel en cas de défaillance d’un pool
ms:assetid: f6303e69-8771-492a-9e8b-c3d7ba231309
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205383(v=OCS.15)
ms:contentKeyID: 49299344
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Expérience de parcage d’appel dans Lync Server 2013 en cas de défaillance d’un pool

 

_**Dernière rubrique modifiée :** 2015-03-09_

Lorsqu’un pool de serveurs frontaux devient indisponible à cause d’un incident imprévu, les appels parqués mais non récupérés sont déconnectés. Durant le basculement vers un pool de sauvegarde, les utilisateurs sont redirigés vers le pool de sauvegarde et placés en mode Résilience. Dans ce mode, les utilisateurs ne peuvent pas parquer les appels, mais ils peuvent les placer en attente et les transférer. Lorsque le basculement est terminé, les appels peuvent de nouveau être parqués et récupérés, comme d’habitude. Durant la restauration automatique, les utilisateurs ne peuvent pas parquer les appels jusqu’à ce qu’ils quittent le mode Résilience.

Durant la récupération d’urgence, les utilisateurs redirigés vers le pool de sauvegarde dans le cadre du processus de basculement utilisent l’application de parcage d’appel déployée dans le pool de sauvegarde. Par conséquent, les utilisateurs redirigés vers le pool de sauvegarde utilisent les paramètres de parcage d’appel configurés pour l’application de parcage d’appel dans le pool de sauvegarde.

Le tableau ci-dessous synthétise les informations relatives à l’utilisation du parcage d’appel via les phases de la récupération d’urgence.

### Expérience utilisateur durant la récupération d’urgence

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>État de l’appel</th>
<th>Lorsqu’une panne se produit</th>
<th>Durant le basculement</th>
<th>Durant la restauration automatique</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Pour les appels non parqués</p></td>
<td><p>Les appels restent connectés, mais ne peuvent pas être parqués.</p></td>
<td><ul>
<li><p>Durant le basculement, les appels ne peuvent pas être parqués pendant que les utilisateurs sont en mode Résilience, mais ils peuvent être mis en attente et transférés.</p></li>
<li><p>Lorsque le basculement est terminé, les appels peuvent être parqués et récupérés.</p></li>
</ul></td>
<td><ul>
<li><p>Durant la restauration automatique, les appels ne peuvent pas être parqués pendant que les utilisateurs sont en mode Résilience, mais ils peuvent être mis en attente et transférés.</p></li>
<li><p>Lorsque la restauration automatique est terminée, les appels peuvent être parqués et récupérés.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Pour les appels parqués, mais non récupérés</p></td>
<td><p>Ces appels sont déconnectés.</p></td>
<td><p>Aucun appel ne reste dans cet état.</p></td>
<td><p>Les appels restent parqués.</p></td>
</tr>
<tr class="odd">
<td><p>Pour les appels parqués déjà récupérés</p></td>
<td><p>Ces appels restent connectés.</p></td>
<td><p>Ces appels restent connectés.</p></td>
<td><p>Ces appels restent connectés.</p></td>
</tr>
</tbody>
</table>

