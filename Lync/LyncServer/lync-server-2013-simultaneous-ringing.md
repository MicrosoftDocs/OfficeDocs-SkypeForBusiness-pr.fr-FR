---
title: 'Lync Server 2013 : Sonnerie simultanée'
TOCTitle: Sonnerie simultanée
ms:assetid: df02f919-4d50-4832-9300-6c51f8b4fc56
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ994079(v=OCS.15)
ms:contentKeyID: 53095548
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Sonnerie simultanée dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Lorsque la sonnerie simultanée est activée pour la partie appelée, le routage géodépendant analyse l’emplacement de l’appelant et les points de terminaison des parties appelées pour déterminer si l’appel doit être routé.

Le tableau ci-dessous illustre un utilisateur pour lequel la sonnerie simultanée est configurée. La cible de la sonnerie simultanée est un utilisateur appartenant au même site réseau, à un autre site réseau ou à un site réseau inconnu.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Appel RTC entrant pour</th>
<th>Situé dans le même site réseau que l’appelé</th>
<th>Situé dans un autre site réseau que l’appelé</th>
<th>Situé dans un site réseau inconnu ou routage géodépendant non activé</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Utilisateur de Lync</p></td>
<td><p>Sonnerie simultanée autorisée</p></td>
<td><p>Sonnerie simultanée non autorisée</p></td>
<td><p>Sonnerie simultanée non autorisée</p></td>
</tr>
</tbody>
</table>

  
Le tableau ci-dessous illustre un appel d’un utilisateur de Lync (appelant Lync) dans le même site réseau, dans un autre site réseau ou dans un site réseau inconnu. L’appelé a un point de terminaison RTC (téléphone portable) configuré comme cible de la sonnerie simultanée. Dans ce scénario, le routage géodépendant détermine si l’appel doit être acheminé ou non vers la cible de sonnerie simultanée (téléphone portable) de l’appelé.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Cible de la sonnerie simultanée</th>
<th>Situé dans le même site réseau que l’appelé</th>
<th>Situé dans un autre site réseau que l’appelé</th>
<th>Situé dans un site réseau inconnu ou routage géodépendant non activé</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Point de terminaison RTC</p></td>
<td><p>Sonnerie simultanée autorisée via la stratégie de routage des communications vocales du site de l’appelant</p></td>
<td><p>Sonnerie simultanée autorisée via la stratégie de routage des communications vocales du site de l’appelant</p></td>
<td><p>Sonnerie simultanée autorisée via la stratégie de voix de l’appelant vers les jonctions sur lesquelles le routage géodépendant n’est pas activé</p></td>
</tr>
</tbody>
</table>


## Voir aussi

#### Autres ressources

[Scénarios de routage géodépendant dans Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)

