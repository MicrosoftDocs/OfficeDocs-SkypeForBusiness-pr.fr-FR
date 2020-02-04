---
title: 'Lync Server 2013 : détails de l’affichage QoE'
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
ms.openlocfilehash: d47fb90b7ffb9eb0cb7fcd1631a0f00ca249276a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724604"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="qoe-view-details-in-lync-server-2013"></a>Détails de l’affichage QoE dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-03_

Les vues couvrent les cas les plus courants de retour de données à partir de la base de données SQL QoE. Il est recommandé d’utiliser des affichages pour créer des rapports personnalisés plutôt que d’accéder directement aux tables de la base de données. en effet, les vues sont plus susceptibles de garantir la compatibilité descendante avec les versions ultérieures.


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
<td><p><a href="lync-server-2013-audiostreamdetail-view.md">Affichage AudioStreamDetail dans Lync Server 2013</a></p></td>
<td><p>Stocke les informations relatives à chaque flux audio dans la base de données.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-medialine-view.md">Affichage MediaLine dans Lync Server 2013</a></p></td>
<td><p>Stocke les informations relatives à chaque ligne multimédia dans la base de données. Une seule session audio contient généralement une ligne multimédia audio. Une session audio et vidéo (A/V) contient généralement une seule ligne de médias audio et une seule ligne de média vidéo. Toutefois, la session peut contenir deux lignes de média vidéo si un appareil de conférence est utilisé ou si la vue Galerie est utilisée.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-networkconfigurationsettings-view.md">Affichage NetworkConfigurationSettings dans Lync Server 2013</a></p></td>
<td><p>Stocke des informations sur la configuration du réseau.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-session-view.md">Affichage de session dans Lync Server 2013</a></p></td>
<td><p>Stocke les informations sur les sessions contenant des enregistrements dans la base de données.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragent-view.md">Affichage UserAgent dans Lync Server 2013</a></p></td>
<td><p>Stocke les informations sur les agents utilisateur impliqués dans les sessions contenant des enregistrements dans la base de données.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videostreamdetail-view.md">Affichage VideoStreamDetail dans Lync Server 2013</a></p></td>
<td><p>Stocke des informations sur chaque flux vidéo dans la base de données.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

