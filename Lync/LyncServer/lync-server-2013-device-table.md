---
title: 'Lync Server 2013 : Table Device'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Device table
ms:assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398930(v=OCS.15)
ms:contentKeyID: 48185544
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 974898f6c3fa96dd9356a0a9eed1e3fab09d288b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831430"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-table-in-lync-server-2013"></a>Table Device dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-02_

La table Device est une table qui contient des informations sur les différents périphériques de capture ou de rendu. Chaque enregistrement de la table représente un appareil.


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
<td><p><strong>DeviceKey</strong></p></td>
<td><p>int</p></td>
<td><p>Principal</p></td>
<td><p>Numéro unique identifiant cet appareil.</p></td>
</tr>
<tr class="even">
<td><p><strong>Périphérique</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nom_unité + DeviceType est unique</p></td>
<td><p>Nom de l’appareil.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceType</strong></p></td>
<td><p>bit</p></td>
<td><p>Nom_unité + DeviceType est unique</p></td>
<td><p>Type d’appareil. 1 est un appareil de capture; 0 est un périphérique de rendu.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

