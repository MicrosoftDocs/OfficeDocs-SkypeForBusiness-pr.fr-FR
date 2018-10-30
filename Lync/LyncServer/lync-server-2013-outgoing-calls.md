---
title: 'Lync Server 2013 : Appels sortants'
TOCTitle: Appels sortants
ms:assetid: 885ffe6f-cd51-4f21-8d4f-a1ff8d818858
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ994049(v=OCS.15)
ms:contentKeyID: 53095470
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Appels sortants dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Le routage des appels sortants des utilisateurs pour lesquels le routage géodépendant est activé est affecté par l’emplacement réseau du point de terminaison de l’utilisateur. Le tableau ci-dessous illustre la façon dont le routage géodépendant affecte le routage des appels sortants selon l’emplacement du point de terminaison de l’appelant.

### Appelant passant un appel sortant vers le réseau téléphonique commuté (RTC)

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Point de terminaison d’un utilisateur situé dans un site réseau pour lequel le routage géodépendant est activé</th>
<th>Point de terminaison de l’utilisateur situé dans un site réseau inconnu ou pour lequel le routage géodépendant n’est pas activé</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Autorisation des appels sortants</p></td>
<td><p>L’appel est autorisé sur la base de la stratégie de voix de l’utilisateur</p></td>
<td><p>L’appel est autorisé sur la base de la stratégie de voix de l’utilisateur</p></td>
</tr>
<tr class="even">
<td><p>Routage de l’appel sortant</p></td>
<td><p>L’appel est routé selon le stratégie de routage des communications vocales du site réseau</p></td>
<td><p>L’appel est routé selon la stratégie de voix de l’utilisateur en utilisant uniquement des jonctions pour lesquelles le routage géodépendant n’est pas activé (si celui-ci est disponible)</p></td>
</tr>
</tbody>
</table>


## Voir aussi

#### Autres ressources

[Scénarios de routage géodépendant dans Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)

