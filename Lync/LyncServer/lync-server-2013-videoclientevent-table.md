---
title: 'Lync Server 2013 : Table VideoClientEvent'
TOCTitle: Table VideoClientEvent
ms:assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg399039(v=OCS.15)
ms:contentKeyID: 49299194
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table VideoClientEvent dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Chaque enregistrement contient un événement client pour un point de terminaison dans un appel vidéo. En général, un appel a deux enregistrements, un pour l’appelant et un pour l’appelé.


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
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Principal</p></td>
<td><p>Référencée depuis la <a href="lync-server-2013-medialine-table.md">Table MediaLine dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Principal</p></td>
<td><p>Référencée depuis la <a href="lync-server-2013-medialine-table.md">Table MediaLine dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Principal</p></td>
<td><p>Référencée depuis la <a href="lync-server-2013-medialine-table.md">Table MediaLine dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromCaller</strong></p></td>
<td><p>bit</p></td>
<td><p>Principal</p></td>
<td><p>0 : Données de l’appelé</p>
<p>1 : Données de l’appelant</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkBandwidthLowEventRatio</strong></p></td>
<td><p></p></td>
<td><p> </p></td>
<td><p>Pourcentage de session auquel l’événement LowBandwidth a été déclenché pour cause d’état « incorrect ». La bande passante disponible est insuffisante pour une utilisation acceptable de la voix.</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkReceiveQualityEventRatio</strong></p></td>
<td><p></p></td>
<td><p> </p></td>
<td><p>Pourcentage de session auquel l’événement ReceiveSendQuality a été déclenché pour cause d’état « incorrect ».</p>
<p>La qualité du réseau en termes de gigue ou de perte de paquets est lourde et elle a des répercussions sur la qualité de l’audio reçu.</p></td>
</tr>
</tbody>
</table>

