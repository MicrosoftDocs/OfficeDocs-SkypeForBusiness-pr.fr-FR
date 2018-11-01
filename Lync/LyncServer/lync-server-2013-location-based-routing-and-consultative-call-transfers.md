---
title: Routage géodépendant et transferts d’appel consultatifs
TOCTitle: Routage géodépendant et transferts d’appel consultatifs
ms:assetid: b12460c2-36c8-481f-b867-fe10dc1c0bdf
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn362836(v=OCS.15)
ms:contentKeyID: 56269642
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Routage géodépendant et transferts d’appel consultatifs

 

_**Dernière rubrique modifiée :** 2015-03-09_

Outre l’application du routage géodépendant aux réunions Lync, l’application de conférence avec routage géodépendant applique des restrictions de routage géodépendant aux transferts d’appel consultatifs dirigés vers des points de terminaison PSTN. Un transfert d’appel consultatif est un appel établi entre deux parties dans lequel une des parties transfère l’appel vers un nouvel utilisateur. Par exemple, un point de terminaison PSTN appelle l’utilisateur A (appelé Lync). L’utilisateur A détermine que l’appel de l’utilisateur PSTN doit être transmis à l’utilisateur B (utilisateur Lync). L’utilisateur A passe l’appel avec l’utilisateur PSTN en attente, et appelle l’utilisateur B. L’utilisateur B accepte de parler à l’utilisateur PSTN. L’utilisateur A transfère l’appel en attente à l’utilisateur B.

**Flux des transferts d’appel consultatifs**

![Diagramme Routage géodépendant pour les conférences](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Diagramme Routage géodépendant pour les conférences")

Lorsqu’un utilisateur activé pour le routage géodépendant lance un transfert d’appel consultatif d’un point de terminaison PSTN (comme indiqué dans la figure précédente), ceci crée deux appels actifs : un appel entre l’utilisateur PSTN et l’utilisateur Lync A, et l’autre entre l’utilisateur Lync A et l’utilisateur Lync B. Le comportement suivant est appliqué par l’application de conférence avec routage géodépendant :

  - Si la jonction SIP routant l’appel PSTN est autorisée à réacheminer l’appel PSTN vers le site réseau dans lequel l’utilisateur Lync B (cible de transfert) est situé, le transfert d’appel est autorisé. Sinon, le transfert d’appel consultatif est bloqué. Cette autorisation est octroyée selon l’appartenance de la partie transférée au même site réseau que la jonction SIP qui route l’appel actif vers le point de terminaison PSTN.

  - Si la jonction SIP qui route l’appel PSTN entrant n’est pas autorisée à acheminer les appels vers le site réseau dans lequel la partie transférée (utilisateur Lync B) est situé ou si la partie transférée est située dans un site réseau inconnu, le transfert d’appel consultatif vers le point de terminaison PSTN (cible de transfert d’appel) est bloqué.

Le tableau suivant décrit l’application des restrictions de routage géodépendant par l’application de conférence avec routage géodépendant pour les transferts d’appel consultatifs. Si les points de terminaison PBX ne sont pas directement associés à un site réseau, la jonction SIP à laquelle le PBX est connecté peut être affectée à un site réseau. Par conséquent, le point de terminaison PBX peut être indirectement associé à un site réseau.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Site réseau de la partie dont l’appel est transféré</p></td>
<td><p>Site réseau de la cible de transfert d’appel</p></td>
<td><p>Comportement</p></td>
</tr>
<tr class="even">
<td><p>Point de terminaison PSTN</p></td>
<td><p>Utilisateur Lync dans le même site réseau (site 1)</p></td>
<td><p>Le transfert consultatif est autorisé</p></td>
</tr>
<tr class="odd">
<td><p>Point de terminaison PSTN</p></td>
<td><p>Utilisateur Lync dans un autre site réseau (site 2)</p></td>
<td><p>Le transfert consultatif n’est pas autorisé</p></td>
</tr>
<tr class="even">
<td><p>Point de terminaison PSTN</p></td>
<td><p>Utilisateur Lync dans un site réseau inconnu</p></td>
<td><p>Le transfert consultatif n’est pas autorisé</p></td>
</tr>
<tr class="odd">
<td><p>Point de terminaison PSTN</p></td>
<td><p>Utilisateur Lync fédéré</p></td>
<td><p>Le transfert consultatif n’est pas autorisé</p></td>
</tr>
<tr class="even">
<td><p>Point de terminaison PSTN</p></td>
<td><p>Point de terminaison PBX dans le même site (site 1)</p></td>
<td><p>Le transfert consultatif est autorisé</p></td>
</tr>
<tr class="odd">
<td><p>Point de terminaison PSTN</p></td>
<td><p>Point de terminaison PBX dans un autre site (site 2)</p></td>
<td><p>Le transfert consultatif n’est pas autorisé</p></td>
</tr>
<tr class="even">
<td><p>Point de terminaison PBX dans le même site (site 1)</p></td>
<td><p>Point de terminaison PSTN</p></td>
<td><p>Le transfert consultatif est autorisé</p></td>
</tr>
<tr class="odd">
<td><p>Point de terminaison PBX dans un autre site (site 2)</p></td>
<td><p>Point de terminaison PSTN</p></td>
<td><p>Le transfert consultatif n’est pas autorisé</p></td>
</tr>
<tr class="even">
<td><p>Point de terminaison PBX dans un site quelconque</p></td>
<td><p>Utilisateur Lync dans le même site réseau (site 1)</p></td>
<td><p>Le transfert consultatif est autorisé</p></td>
</tr>
<tr class="odd">
<td><p>Point de terminaison PBX dans un site quelconque</p></td>
<td><p>Utilisateur Lync dans un autre site réseau (site 2)</p></td>
<td><p>Le transfert consultatif est autorisé</p></td>
</tr>
<tr class="even">
<td><p>Point de terminaison PBX dans un site quelconque</p></td>
<td><p>Utilisateur Lync dans un site réseau inconnu</p></td>
<td><p>Le transfert consultatif est autorisé</p></td>
</tr>
<tr class="odd">
<td><p>Point de terminaison PBX dans un site quelconque</p></td>
<td><p>Utilisateur Lync fédéré</p></td>
<td><p>Le transfert consultatif est autorisé</p></td>
</tr>
</tbody>
</table>

