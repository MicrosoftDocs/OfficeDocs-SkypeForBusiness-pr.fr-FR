---
title: 'Lync Server 2013: surveillance des performances du stockage principal de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring back end Lync Server 2013 storage performance
ms:assetid: 71627c70-1953-4ac2-afbe-f3ad85be0f44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720917(v=OCS.15)
ms:contentKeyID: 63969619
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4c63956cebc7f532f92b6e0729bdfe811d0fdfb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826758"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-back-end-lync-server-2013-storage-performance"></a>Surveiller les performances de stockage de Lync Server 2013 en arrière-plan

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-05-02_

Les bases de données principales de Lync Server 2013 constituent un élément essentiel du déploiement de Lync Server 2013. Nous vous recommandons de surveiller en permanence les bases de données et les journaux de transactions correspondants pour vous assurer que le serveur Lync Server 2013 fonctionne de façon optimale.

Le tableau suivant identifie les compteurs de performance qui doivent être surveillés pour en savoir plus sur les performances de stockage. Les valeurs de référence de ces compteurs doivent d’abord être définies (lorsque le système se trouve à sa normale, charge attendue) pour comprendre les changements de performance lorsque le système est surchargé.

### <a name="performance-counters-to-be-monitored"></a>Compteurs de performance à surveiller

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Compteur de performance</th>
<th>Seuils de référence</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Transactions/s (RTC)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Transactions/s (RTCDyn)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Transactions/s (tempdb)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Vidages du journal/s (RTC)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Vidages du journal/s (RTCDyn)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Vidages du journal/s (tempdb)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Transferts de disque/s (lecture + écriture)-RTC DB</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Transferts de disque/s-journal RTC</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Transferts de disque/s-RTCDyn DB</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Transfert de disque/s-journal de RTCDyn</p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

