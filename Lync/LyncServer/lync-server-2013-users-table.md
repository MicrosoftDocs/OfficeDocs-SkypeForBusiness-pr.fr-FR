---
title: 'Lync Server 2013 : Table Users'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Users table
ms:assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412791(v=OCS.15)
ms:contentKeyID: 48185032
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2be643f8a593af01ee47ad93d3910d44ee86e48
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744324"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="users-table-in-lync-server-2013"></a>Table Users dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-28_

La table users est une table de prise en charge. Chaque enregistrement de la table stocke des informations relatives à un utilisateur impliqué dans des appels ou des sessions ayant des enregistrements dans la base de données.


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
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>DateHeure</p></td>
<td></td>
<td><p>Horodatage pour un usage interne.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>Principal</p></td>
<td><p>Numéro unique identifiant cet utilisateur.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p> </p></td>
<td><p>URI de l’utilisateur.</p></td>
</tr>
<tr class="even">
<td><p><strong>IDClient</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>ID de client de cet utilisateur. Pour plus d’informations, voir la <a href="lync-server-2013-tenants-table.md">table locataires dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>UriTypeId</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>Type d’URI de cet utilisateur. Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

