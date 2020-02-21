---
title: 'Lync Server 2013 : table DeviceDriver'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DeviceDriver table
ms:assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398844(v=OCS.15)
ms:contentKeyID: 48185449
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2813ac26bbfd21aa35dbe71c9c4477e8107b8967
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214382"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="devicedriver-table-in-lync-server-2013"></a>Table DeviceDriver dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-02_

La table DeviceDriver est une table de prise en charge. Chaque enregistrement représente un pilote utilisé par un périphérique de capture ou par un périphérique de rendu.


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
<td><p><strong>DeviceDriverKey</strong></p></td>
<td><p>int</p></td>
<td><p>Primaire</p></td>
<td><p>Numéro unique d’identification de cet enregistrement de pilote de périphérique.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceDriver</strong></p></td>
<td><p>varchar (256)</p></td>
<td><p>exclusive</p></td>
<td><p>Nom du pilote de périphérique.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

