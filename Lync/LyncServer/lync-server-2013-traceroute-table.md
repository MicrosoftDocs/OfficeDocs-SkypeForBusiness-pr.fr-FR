---
title: Table TraceRoute dans Lync Server 2013
TOCTitle: Table TraceRoute dans Lync Server 2013
ms:assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205205(v=OCS.15)
ms:contentKeyID: 49298634
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table TraceRoute dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La table TraceRoute contient les informations de routage émanant des appels. Cette table est une nouveauté de Microsoft Lync Server 2013.


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
<td><p>DateHeure</p></td>
<td><p>Primaire, étrangère</p></td>
<td><p>Date et heure de début de l’appel.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primaire, étrangère</p></td>
<td><p>Identificateur unique utilisé pour faire la distinction entre plusieurs appels qui peuvent avoir commencé à la même date et à la même heure.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primaire, étrangère</p></td>
<td><p>Représente le type de ligne vidéo utilisé dans l’appel. Les valeurs autorisées sont les suivantes :</p>
<ul>
<li><p>0 – Audio</p></li>
<li><p>1 – Vidéo</p></li>
<li><p>2 – Vidéo panoramique</p></li>
<li><p>3 – Partage d'application/bureau</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>FromCaller</strong></p></td>
<td><p>bit</p></td>
<td><p>Primaire</p></td>
<td><p>Système d’extrémité qui a passé l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hop</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Tronçon de réseau.</p></td>
</tr>
<tr class="even">
<td><p><strong>IPAddressKey</strong></p></td>
<td><p>int</p></td>
<td><p>Étrangère</p></td>
<td><p>Identificateur unique de l’adresse IP. Les informations d’adresse IP sont stockées dans la <a href="lync-server-2013-ipaddress-table.md">Table IPAddress dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RTT</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Durée de boucle. La durée de boucle mesure le temps nécessaire pour qu’un paquet vocal atteigne sa destination, puis renvoie une notification indiquant qu’il a été reçu.</p></td>
</tr>
</tbody>
</table>

