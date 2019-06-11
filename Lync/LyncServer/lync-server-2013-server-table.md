---
title: 'Lync Server 2013 : Table Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server table
ms:assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398801(v=OCS.15)
ms:contentKeyID: 48184890
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 363c07a6ab3be8f5acdf0286a4223f96a8bd3700
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822005"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-table-in-lync-server-2013"></a>Table Server dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-02_

La table serveur est une table de prise en charge. Chaque enregistrement représente un serveur.


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
<td><p><strong>ServerKey</strong></p></td>
<td><p>int</p></td>
<td><p>Principal</p></td>
<td><p>Numéro unique identifiant le serveur.</p></td>
</tr>
<tr class="even">
<td><p><strong>FQDNOrIP</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>index</p></td>
<td><p>Chaîne d’adresses MAC.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ServerType</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>1: serveur de médiation</p>
<p>2: service de conférence a/V Server16394: service32769 Edge A/V: passerelle</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolName</strong></p></td>
<td><p>nvarchar</p></td>
<td></td>
<td><p>Regroupement auquel appartient le serveur. Applicable uniquement au serveur de conférence A/V.</p></td>
</tr>
<tr class="odd">
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>DateHeure</p></td>
<td></td>
<td><p>Pour un usage interne uniquement.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

