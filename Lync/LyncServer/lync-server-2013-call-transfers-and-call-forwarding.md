---
title: 'Lync Server 2013 : Transferts et renvois d’appels'
TOCTitle: Transferts et renvois d’appels
ms:assetid: 978610ec-63c7-4cf6-ad7a-9ef91559bf12
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ994051(v=OCS.15)
ms:contentKeyID: 53095478
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Transferts et renvois d’appels dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Si un point de terminaison RTC est impliqué, le routage géodépendant analyse l’emplacement du point de terminaison de l’appelé et le point de terminaison vers lequel l’appel sera transféré ou renvoyé (cible de transfert/renvoi). Il détermine si l’appel doit être transféré ou renvoyé selon l’emplacement des deux points de terminaison.

Le tableau ci-dessous illustre un scénario dans lequel l’utilisateur de Lync est en communication avec un point de terminaison RTC et transfère l’appel vers un autre utilisateur de Lync. Selon l’emplacement de site réseau du point de terminaison du cessionnaire, le routage géodépendant affecte le routage du transfert ou du renvoi d’appel.

### Lancement du transfert ou du renvoi d’appel

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Utilisateur à l’origine du transfert/renvoi d’appel</th>
<th>Point de terminaison cible dans le même site réseau que l’utilisateur à l’origine du transfert ou du renvoi d’appel</th>
<th>Point de terminaison cible dans un autre site réseau que l’utilisateur à l’origine du transfert ou du renvoi d’appel</th>
<th>Point de terminaison cible dans un site réseau inconnu ou routage géodépendant non activé sur le site réseau</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Utilisateur de Lync</p></td>
<td><p>Le transfert ou renvoi de l’appel est autorisé</p></td>
<td><p>Le transfert ou renvoi de l’appel n’est pas autorisé</p></td>
<td><p>Le transfert ou renvoi de l’appel n’est pas autorisé</p></td>
</tr>
</tbody>
</table>

  

Par exemple, un utilisateur de Lync en communication avec un point de terminaison RTC transfère l’appel à un autre utilisateur de Lync dans le même site réseau. Dans ce cas, le transfert de l’appel est autorisé.

Le tableau ci-dessous illustre un scénario dans lequel l’utilisateur de Lync est en communication avec un autre utilisateur de Lync. Un des utilisateurs transfère l’appel à un point de terminaison RTC. Selon l’emplacement de l’utilisateur auquel l’appel est transféré, le tableau indique comment le routage géodépendant affecte l’appel.

### Transfert ou renvoi de l’appel vers le point de terminaison RTC

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Point de terminaison cible du transfert/renvoi de l’appel</th>
<th>Utilisateurs de Lync dans le même site réseau</th>
<th>Utilisateurs de Lync dans différents sites réseau</th>
<th>Un des utilisateurs ou les deux dans un site réseau inconnu ou routage géodépendant non activé sur le site réseau</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Point de terminaison RTC</p></td>
<td><p>Le transfert ou le renvoi de l’appel est autorisé par la stratégie de routage des communications vocales du site du cessionnaire</p></td>
<td><p>Le transfert ou le renvoi de l’appel est autorisé par la stratégie de routage des communications vocales du site du cessionnaire</p></td>
<td><p>Le transfert ou le renvoi de l’appel est autorisé par la stratégie de voix du cessionnaire, uniquement via des jonctions pour lesquelles le routage géodépendant n’est pas activé</p></td>
</tr>
</tbody>
</table>

  
Par exemple, un utilisateur de Lync en communication avec un autre utilisateur de Lync dans le même site réseau transfère l’appel à un point de terminaison RTC et le transfert de l’appel est autorisé.

## Voir aussi

#### Autres ressources

[Scénarios de routage géodépendant dans Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)

