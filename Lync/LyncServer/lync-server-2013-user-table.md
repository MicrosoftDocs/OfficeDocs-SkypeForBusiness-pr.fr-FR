---
title: 'Lync Server 2013 : table utilisateur'
description: 'Lync Server 2013 : table utilisateur.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User table
ms:assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398505(v=OCS.15)
ms:contentKeyID: 48184437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15d1ac08a229f4afea35a2727ef1105a5f24b826
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558900"
---
# <a name="user-table-in-lync-server-2013"></a>Table user dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-02_

La table User est une table de prise en charge qui stocke la liste des divers utilisateurs ayant participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente un utilisateur.


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
<td><p><strong>UserKey</strong></p></td>
<td><p>int</p></td>
<td><p>Primaire</p></td>
<td><p>Nombre unique identifiant cet utilisateur.</p></td>
</tr>
<tr class="even">
<td><p><strong>URI</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Uniques</p></td>
<td><p>Chaîne URI.</p></td>
</tr>
<tr class="odd">
<td><p><strong>URIType</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>1 est type URI inconnu.</p>
<p>2 est URI d’utilisateur.</p>
<p>4 est URI de conférence.</p>
<p>8 est URI de téléphone.</p></td>
</tr>
<tr class="even">
<td><p><strong>TenantKey</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger</p></td>
<td><p>Locataire de l’utilisateur, référencé depuis la table de locataires.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LastPoorCallTime</strong></p></td>
<td><p>DateHeure</p></td>
<td></td>
<td><p>Horodatage le plus récent du moment où l’utilisateur avait un appel de mauvaise qualité audio.</p></td>
</tr>
<tr class="even">
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

