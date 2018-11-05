---
title: "Vues détaillées de la qualité de l’exp. (QoE) dans Lync Server 2013"
TOCtitle: "Vues détaillées de la qualité de l’exp. (QoE) dans Lync Server 2013"
ms:assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688081(v=OCS.15)
ms:contentKeyID: 49891382
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vues détaillées de la qualité de l’expérience (QoE, Quality of Experience) dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Les vues couvrent les scénarios les plus courants pour retourner des données de la base de données SQL QoE. Il est recommandé d’utiliser des vues pour générer des rapports personnalisés au lieu d’accéder directement aux tables de base de données. Cela s’explique par le fait que les vues sont plus susceptibles d’offrir une compatibilité descendante avec les versions ultérieures.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Nom de la vue</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-audiostreamdetail-view.md">Vue AudioStreamDetail</a></p></td>
<td><p>Stocke les informations sur chaque flux audio dans la base de données.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-medialine-view.md">Vue MediaLine</a></p></td>
<td><p>Stocke des informations sur chaque ligne de média dans la base de données. Une session audio contient généralement une ligne de média audio. Une session audio et vidéo (A/V) contient généralement une ligne de média audio et une ligne de média vidéo ; toutefois, la session peut contenir deux lignes de média vidéo si un périphérique de conférence ou la Vue Galerie est utilisé.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-networkconfigurationsettings-view.md">Vue NetworkConfigurationSettings</a></p></td>
<td><p>Stocke des informations sur la configuration du réseau.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-session-view.md">Vue Session</a></p></td>
<td><p>Stocke des informations sur les sessions disposant d’enregistrements dans la base de données.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragent-view.md">Vue UserAgent</a></p></td>
<td><p>Stocke des informations sur les agents utilisateurs qui ont participé à des sessions disposant d’enregistrements dans la base de données.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videostreamdetail-view.md">Vue VideoStreamDetail</a></p></td>
<td><p>Stocke des informations sur chaque flux vidéo dans la base de données.</p></td>
</tr>
</tbody>
</table>

