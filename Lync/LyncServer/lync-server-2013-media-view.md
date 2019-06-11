---
title: 'Lync Server 2013: vue multimédia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media view
ms:assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687981(v=OCS.15)
ms:contentKeyID: 49733570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1ec4b80cc790068029a286a54d26a59a35fc125
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827297"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-view-in-lync-server-2013"></a>Vue multimédia dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-01_

Le mode multimédia stocke les informations relatives à un type de média utilisé dans une session d’égal à égal. Une session serait représentée par plusieurs enregistrements dans la table, si plusieurs types de média sont utilisés. Cet affichage a été présenté dans Microsoft Lync Server 2013.

<div>


> [!NOTE]  
> Le mode multimédia ne doit pas être utilisé pour calculer la durée du média pour une session. Cet affichage contient les détails de signalisation d’échange de médias dans une session. L’échange de média est effectué par la demande d’invitation, et la durée de StartTime indique l’heure d’envoi de l’invitation. La durée d’invitation ne correspond pas nécessairement à l’heure de début du média, car le contenu multimédia ne démarre qu’après acceptation de la session.



</div>

La vue multimédia contient toutes les colonnes de la [vue SessionDetails dans Lync Server 2013](lync-server-2013-sessiondetails-view.md) , en plus de celles répertoriées ci-dessous.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Colonne</th>
<th>Type de données</th>
<th>Détails</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Media</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Type de média. Pour plus d’informations, reportez-vous <a href="lync-server-2013-medialist-table.md">à la table de médiane dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>MediaStartTime</strong></p></td>
<td><p>DateHeure</p></td>
<td><p>Temps d’envoi d’une demande de média.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaEndTime</strong></p></td>
<td><p>DateHeure</p></td>
<td><p>Heure de fin de la session.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

