---
title: 'Lync Server 2013 : données d’affichage de QoE'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoE view details
ms:assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688081(v=OCS.15)
ms:contentKeyID: 49733677
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f6d2b30654272baf0ce8db712461acb3e4f13a6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138905"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="qoe-view-details-in-lync-server-2013"></a>QoE afficher les détails dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-03_

Les affichages couvrent les scénarios les plus courants pour le renvoi de données à partir de la base de données de QoE SQL. Il s’agit des vues recommandées utilisées pour créer des rapports personnalisés au lieu d’accéder directement aux tables de base de données ; Cela est dû au fait que les vues ont plus de chances de conserver une compatibilité descendante avec les versions ultérieures.


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
<td><p><a href="lync-server-2013-audiostreamdetail-view.md">Vue AudioStreamDetail dans Lync Server 2013</a></p></td>
<td><p>Stocke les informations sur chaque flux audio dans la base de données.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-medialine-view.md">Vue MediaLine dans Lync Server 2013</a></p></td>
<td><p>Stocke des informations sur chaque ligne de média dans la base de données. Une session audio contient généralement une ligne de média audio. Une session audio et vidéo (A/V) contient généralement une ligne de média audio et une ligne de média vidéo ; toutefois, la session peut contenir deux lignes de média vidéo si un périphérique de conférence ou la Vue Galerie est utilisé.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-networkconfigurationsettings-view.md">Vue NetworkConfigurationSettings dans Lync Server 2013</a></p></td>
<td><p>Stocke des informations sur la configuration du réseau.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-session-view.md">Vue de session dans Lync Server 2013</a></p></td>
<td><p>Stocke des informations sur les sessions disposant d’enregistrements dans la base de données.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragent-view.md">Vue UserAgent dans Lync Server 2013</a></p></td>
<td><p>Stocke des informations sur les agents utilisateurs qui ont participé à des sessions disposant d’enregistrements dans la base de données.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videostreamdetail-view.md">Vue VideoStreamDetail dans Lync Server 2013</a></p></td>
<td><p>Stocke des informations sur chaque flux vidéo dans la base de données.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

