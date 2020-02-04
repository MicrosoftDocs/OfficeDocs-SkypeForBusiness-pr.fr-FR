---
title: 'Lync Server 2013 : tblRoleType'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblRoleType
ms:assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558623(v=OCS.15)
ms:contentKeyID: 48183577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba6b5041453b0965fafc12ada2be62ec42316f89
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731184"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblroletype-in-lync-server-2013"></a>tblRoleType dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-06-25_

tblRoleType est une table de recherche statique avec les types de rôles et leurs jeux d’autorisations associés.

### <a name="columns"></a>Celles

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Colonne</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>rtypeID</p></td>
<td><p>ent, non null</p></td>
<td><p>ID du type de rôle.</p></td>
</tr>
<tr class="even">
<td><p>rtypeDesc</p></td>
<td><p>nvarchar (256), pas null</p></td>
<td><p>Description du type de rôle. Il existe quatre rôles disponibles :</p>
<ul>
<li><p>Membre : membres de salle de conversation</p></li>
<li><p>Manager : gestionnaire de salle de conversation</p></li>
<li><p>Voix : présentateur pour une salle de conversation Auditorium</p></li>
<li><p>Créateur : peut créer des salles de conversation</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>rtypeAllowedPermSet</p></td>
<td><p>bigint, pas null</p></td>
<td><p>Autorisation définie pour le rôle. Les bits utilisés sont les suivants :</p>
<ul>
<li><p>2 : true si le rôle peut gérer des nœuds.</p></li>
<li><p>4 : true si le rôle peut créer des nœuds enfants.</p></li>
<li><p>7 : true si le rôle peut rejoindre une salle de conversation (ou des salles de conversation enfant d’une catégorie).</p></li>
<li><p>8 : true si le rôle peut discuter dans une salle de conversation (ou dans des salles de conversation enfant d’une catégorie).</p></li>
<li><p>10 : true si le rôle peut lire l’historique des conversations même en l’absence de participation à une salle de conversation.</p></li>
<li><p>11 : true si le rôle peut voir la salle de conversation. (Cette valeur est améliorée par des facteurs tels que Scope et Visibility.)</p></li>
<li><p>12 : true si le rôle peut discuter dans une salle de conversation Auditorium.</p></li>
<li><p>13 : true si le rôle peut ignorer les règles de visibilité lors de la consultation des nœuds.</p></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="key"></a>Clé

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Colonne</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>rtypeID</p></td>
<td><p>Clé primaire.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

