---
title: 'Tableau Lync Server 2013: SIPResponseMetaData'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SIPResponseMetaData table
ms:assetid: cf723737-4a75-4352-829b-f4954aa59716
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205294(v=OCS.15)
ms:contentKeyID: 48185510
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31df563172cce2e6ac9780511665ef563532a7d9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846801"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sipresponsemetadata-table-in-lync-server-2013"></a>Table SIPResponseMetaData dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-28_

Le SIPResponseMetaDataTable contient une liste des codes de réponse SIP et la classification et la définition de chacun de ces codes. Ces codes sont générés en réponse à des événements affectant des périphériques SIP et des sessions de communication SIP; par exemple, le code de réponse 403 est généré lorsqu’un périphérique SIP envoie une demande, mais que le serveur décline la demande.

Ce tableau a été présenté dans Microsoft Lync Server 2013.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Colonne</th>
<th>Type de données</th>
<th>Clé/Index</th>
<th>Détails</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>Principal</p></td>
<td><p>Valeur numérique qui représente le code de réponse SIP.</p></td>
</tr>
<tr class="even">
<td><p><strong>Cours</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Classification générale du code de réponse. Les classifications sont les suivantes:</p>
<ul>
<li><p>1 – réponses d’information</p></li>
<li><p>2 – réponses réussies</p></li>
<li><p>3 – réponses de redirection</p></li>
<li><p>4 – réponses d’échec client</p></li>
<li><p>5 réponses aux échecs sur le serveur</p></li>
<li><p>6-réponse d’échec globale</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td></td>
<td><p>Description du code de réponse SIP. Par exemple, le code de réponse 181 contient la description suivante:</p>
<p>Appel en cours de transfert</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

