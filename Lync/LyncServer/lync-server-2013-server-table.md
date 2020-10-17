---
title: 'Lync Server 2013 : table serveur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server table
ms:assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398801(v=OCS.15)
ms:contentKeyID: 48184890
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ebfc08cd5a27527d5afebdae8b2fea8335f93dcb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510231"
---
# <a name="server-table-in-lync-server-2013"></a>Table serveur dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-02_

Le tableau serveur est une table de prise en charge. Chaque enregistrement représente un serveur.


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
<th><strong>Clé/index</strong></th>
<th><strong>Details</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ServerKey</strong></p></td>
<td><p>int</p></td>
<td><p>Primaire</p></td>
<td><p>Numéro unique identifiant le serveur.</p></td>
</tr>
<tr class="even">
<td><p><strong>FQDNOrIP</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Index</p></td>
<td><p>Chaîne d’adresse MAC.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ServerType</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger</p></td>
<td><p>1 : serveur de médiation</p>
<p>2 : Conférence a/V Server16394 : service32769 Edge A/V : passerelle</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolName</strong></p></td>
<td><p>nvarchar</p></td>
<td></td>
<td><p>Pool auquel appartient le serveur. Applicable uniquement au serveur de conférence A/V.</p></td>
</tr>
<tr class="odd">
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>DateHeure</p></td>
<td></td>
<td><p>À usage interne uniquement.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

