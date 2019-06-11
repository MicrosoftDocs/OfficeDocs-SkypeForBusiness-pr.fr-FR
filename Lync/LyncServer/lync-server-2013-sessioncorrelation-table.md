---
title: 'Lync Server 2013 : Table SessionCorrelation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SessionCorrelation table
ms:assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398091(v=OCS.15)
ms:contentKeyID: 48183267
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c588a58126fb83df08550a6300ca8db36cceb647
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34821949"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessioncorrelation-table-in-lync-server-2013"></a>Table SessionCorrelation dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-02_

La table SessionCorrelation est une table de prise en charge. Chaque enregistrement représente une corrélation qui est utilisée pour mettre en corrélation plusieurs sessions.


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
<td><p><strong>1018</strong></p></td>
<td><p>int</p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><strong>CorrelationKey</strong></p></td>
<td><p>int</p></td>
<td><p>Principal</p></td>
<td><p>Numéro unique identifiant ce serveur de conférence A/V.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Corrélation</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Différent</p></td>
<td><p>Les sessions corrélées auront le même ID de corrélation.</p></td>
</tr>
<tr class="even">
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>DateHeure</p></td>
<td><p> </p></td>
<td><p>Pour un usage interne uniquement.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

