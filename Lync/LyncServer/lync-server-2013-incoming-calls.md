---
title: 'Lync Server 2013 : Appels entrants'
TOCTitle: Appels entrants
ms:assetid: 65b9c1b4-6af7-4527-8c33-22c4442bd209
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ994038(v=OCS.15)
ms:contentKeyID: 53095441
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Appels entrants dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Le routage des appels entrants vers les utilisateurs pour lesquels le routage géodépendant est activé dépend de l’emplacement du point de terminaison de l’utilisateur. Si un utilisateur reçoit un appel entrant au niveau d’un point de terminaison situé dans un site réseau sur lequel le routage géodépendant est activé, et si le point de terminaison est situé dans le même site réseau que la passerelle RTC, l’appel est acheminé. Si un utilisateur reçoit un appel entrant au niveau d’un point de terminaison situé dans un site réseau sur lequel le routage géodépendant est activé, et si le point de terminaison est situé dans un autre site réseau que la passerelle RTC, l’appel n’est pas acheminé. Si un utilisateur n’a aucun point de terminaison situé dans le même site réseau que la passerelle RTC dont provient l’appel entrant, ce dernier est acheminé directement vers la messagerie vocale de l’utilisateur et une notification d’appel manqué est envoyée au destinataire de l’appel.

Les paramètres de transfert d’appel d’un utilisateur pour lequel le routage géodépendant est activé restent appliqués. Les appels transmis sont toutefois soumis aux restrictions de routage géodépendant de l’utilisateur.

Le tableau ci-dessous illustre la façon dont le routage géodépendant affecte le routage des appels entrants selon l’emplacement du point de terminaison de l’appelé. Le routage géodépendant est activé sur le site réseau de la passerelle RTC et ne permet que le routage des appels RTC vers les points de terminaison au sein du même site réseau.

### Appelé recevant un appel entrant à partir de la passerelle RTC

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Point de terminaison de l’appelé situé dans le même site réseau que la passerelle RTC</th>
<th>Point de terminaison de l’appelé non situé dans le même site réseau que la passerelle RTC</th>
<th>Point de terminaison de l’appelé situé dans un site réseau inconnu ou pour lequel le routage géodépendant n’est pas activé</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Routage de l’appel RTC entrant</p></td>
<td><p>L’appel entrant est routé vers les points de terminaison de l’appelé</p></td>
<td><p>L’appel entrant n‘est pas routé vers les points de terminaison de l’appelé</p></td>
<td><p>L’appel entrant n‘est pas routé vers les points de terminaison de l’appelé</p></td>
</tr>
</tbody>
</table>

  

## Voir aussi

#### Autres ressources

[Scénarios de routage géodépendant dans Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)

