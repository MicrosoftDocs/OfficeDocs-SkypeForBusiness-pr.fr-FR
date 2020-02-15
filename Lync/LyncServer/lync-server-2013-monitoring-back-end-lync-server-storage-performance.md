---
title: 'Lync Server 2013 : analyse des performances de stockage back-end Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring back end Lync Server 2013 storage performance
ms:assetid: 71627c70-1953-4ac2-afbe-f3ad85be0f44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720917(v=OCS.15)
ms:contentKeyID: 63969619
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 760e66403fd1da2b5a45cf0db065dc201e1fd02a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051156"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-back-end-lync-server-2013-storage-performance"></a>Surveillance des performances de stockage principales de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-05-02_

Les bases de données principales Lync Server 2013 sont un élément très important du déploiement de Lync Server 2013. Nous vous recommandons de surveiller en permanence les bases de données et les journaux de transactions respectifs afin de s’assurer que le serveur principal Lync Server 2013 fonctionne de manière optimale.

Le tableau suivant identifie les compteurs de performance qui doivent être surveillés afin d’obtenir des informations sur les performances de stockage. Les valeurs de base de ces compteurs doivent être définies en premier (lorsque le système est à sa charge normale et attendue) pour comprendre les changements de performances lorsque le système est surchargé.

### <a name="performance-counters-to-be-monitored"></a>Compteurs de performance à surveiller

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Compteur de performance</th>
<th>Seuils de ligne de base</th>
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
<td><p>Transferts disque/s (lecture + écriture)-RTC DB</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Transferts disque/s-journal RTC</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Transferts disque/s-RTCDyn DB</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Transferts disque/s-journal RTCDyn</p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

