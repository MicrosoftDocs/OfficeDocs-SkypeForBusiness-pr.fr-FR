---
title: 'Lync Server 2013 : table de médiane'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaList table
ms:assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398279(v=OCS.15)
ms:contentKeyID: 48183579
ms.date: 07/12/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66a0e59d979c3356d244bb341fcdfabae5b7addc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217570"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="medialist-table-in-lync-server-2013"></a>Table médial dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-07-12_

La table MediaList est une table statique qui stocke la liste de divers types de médias.


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
<th>Clé/index</th>
<th>Détails</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>MediaId</strong></p></td>
<td><p>entier très petit</p></td>
<td><p>Primaire</p></td>
<td><p>Valeurs : 1-7</p></td>
</tr>
<tr class="even">
<td><p><strong>Support</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td></td>
<td><p>Mappage statique des valeurs MediaID et multimédias :</p>
<ul>
<li><p>1 – MESSAGERIE INSTANTANÉE</p></li>
<li><p>2 – Transfert de fichiers</p></li>
<li><p>3 – Assistance à distance</p></li>
<li><p>4 – Partage d’application</p></li>
<li><p>5 – audio</p></li>
<li><p>6 – vidéo</p></li>
<li><p>7 – Invitation d’application</p></li>
</ul></td>
</tr>
</tbody>
</table>


Si vous tentez de déterminer le type de modalité pour les valeurs dans LcsCDR. SessionDetailsView. MediaTypes, vous devez utiliser l’extrait de code de jointure suivant :

    LEFT JOIN on Media.MediaId = MediaList.MediaId

</div>

<span> </span>

</div>

</div>

</div>

